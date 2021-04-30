# es_extended1.1

FiveM Weight Item
esx_inventoryhud/html/js/inventory.js

Dfault

else if (event.data.action == "setItems") {
        inventorySetup(event.data.itemList);
		$(".info-div2").html(event.data.text);
		
		$("#fWeight").html(event.data.weight / 1000);
		$("#fMaxWeight").html(event.data.max / 1000);

        $('.item').draggable({
            appendTo: 'body',
            zIndex: 99999,
			disabled: false,
			drag: function(event, ui) {
				ui.position.left = ui.position.left+5;
				ui.position.top = ui.position.top+5;
			},
            helper: function(e) {
				var original = $(e.target).hasClass("ui-draggable") ? $(e.target) :  $(e.target).closest(".ui-draggable");
				return original.clone().css({
					width: original.width(),
					height: original.height(),
				});                
			},
            stop: function () {
                itemData = $(this).data("item");

                if (itemData !== undefined && itemData.name !== undefined) {
                    $(this).css('background-image', 'url(\'img/items/' + itemData.name + '.png\'');
                    $("#use").removeClass("disabled");
                    $("#give").removeClass("disabled");
                }
            }
        });
        

  else if (event.data.action == "setItems") {
        inventorySetup(event.data.itemList);
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
		// $("#fWeight").html(event.data.weight / 1000);
		// $("#fMaxWeight").html(event.data.max / 1000);

        $('.item').draggable({
            appendTo: 'body',
            zIndex: 99999,
			disabled: false,
			drag: function(event, ui) {
				ui.position.left = ui.position.left+5;
				ui.position.top = ui.position.top+5;
			},
            helper: function(e) {
				var original = $(e.target).hasClass("ui-draggable") ? $(e.target) :  $(e.target).closest(".ui-draggable");
				return original.clone().css({
					width: original.width(),
					height: original.height(),
				});                
			},
            stop: function () {
                itemData = $(this).data("item");

                if (itemData !== undefined && itemData.name !== undefined) {
                    $(this).css('background-image', 'url(\'img/items/' + itemData.name + '.png\'');
                    $("#use").removeClass("disabled");
                    $("#give").removeClass("disabled");
                }
            }
        });
