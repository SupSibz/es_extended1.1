# es_extended 1.1.0
```
FiveM Weight Item
Path File
esx_inventoryhud/html/js/inventory.js
esx_inventoryhud/html/ui.html
```

# Javascript
```javascript
ค้นหา
 if (event.data.action == "setItems") {
        inventorySetup(event.data.itemList);
        เพิ่ม
        let { carryWeight, maxCarryWeight } = event.data;
         carryWeight = carryWeight / 1000
        carryWeight = carryWeight.toLocaleString('en-US', {
            maximumFractionDigits: 1
        })
        maxCarryWeight = maxCarryWeight / 1000
        maxCarryWeight = maxCarryWeight.toLocaleString('en-US', {
            maximumFractionDigits: 1
        })
        let weight = `นํ้าหนักกระเป๋าคุณ ${carryWeight} / ${maxCarryWeight} KG`
		$("#carry-weight").html(weight)
		$(".info-div2").html(event.data.text);
```

# Main Server
```lua

ESX.RegisterServerCallback('esx:getPlayerCarryWeight', function(source, cb)
	local xPlayer = ESX.GetPlayerFromId(source)
	cb(ESX.CarryWeight(xPlayer), Config.MaxCarryWeight)
end)
```

# Function Server
```lua

 ESX.CarryWeight = function(xPlayer)
	local _invData = xPlayer.getInventory()
	local _carryWeight = 0
	for i=1, #_invData do
		local itemName = _invData[i].name
		local itemCount = _invData[i].count
		_carryWeight = _carryWeight + (ESX.Items[itemName].weight * itemCount)
	end
	return _carryWeight
end

ESX.isOverCarry = function(xPlayer)
	if ESX.CarryWeight(xPlayer) > Config.MaxCarryWeight then
		TriggerClientEvent("esx:overcarry", xPlayer.source, true)
	else
		TriggerClientEvent("esx:overcarry", xPlayer.source, false)
	end
end

```

# HTML
```html

 <div id="carry-weight">0 / 50kg</div>
```

# SQL
```
เพิ่ม SQL item
 Name : weight
 Datatype : INT
 Default : 0
```
