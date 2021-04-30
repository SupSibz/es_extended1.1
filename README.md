# es_extended1.1

FiveM Weight Item
esx_inventoryhud/html/js/inventory.js

# ค้นหา
```lua

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
