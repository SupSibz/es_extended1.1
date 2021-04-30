# es_extended1.1

FiveM Weight Item
esx_inventoryhud/html/js/inventory.js

# API
```lua
vSql.Async.execute(query, parameters, callback)
vSql.Async.transaction(queries, parameters, callback)

vSql.Async.fetchScalar(query, parameters, callback)
vSql.Async.fetchAll(query, parameters, callback)
```

ค้นหา 

 if (event.data.action == "setItems") {
        inventorySetup(event.data.itemList);
