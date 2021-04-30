# es_extended 1.1.0
```
FiveM Weight Item
Path File
esx_inventoryhud/html/js/inventory.js
esx_inventoryhud/html/ui.html
```

# Javascript
```lua
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

# HTML
```html

 <div id="carry-weight">0 / 50kg</div>
```

# SQL
```
 Name : weight
 Datatype : INT
 Default : 0
```
