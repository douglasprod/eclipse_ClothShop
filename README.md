## [ESX]Eclipse ClothShop

## Requirements
- [plume-esx](https://youtu.be/iGfwUCO0RZQ) (you can use different version esx)
- [esx-skin](https://github.com/esx-framework/esx_skin)
- [skinchanger](https://github.com/ESX-Org/skinchanger)


Put eclipse_TattooShopp in your resource directory

Setting config `resources\eclipse_BarberShop\config.json`

	Change language, add new shops, change prices and etc.
  ![image](https://user-images.githubusercontent.com/36680471/154804190-c570fa2e-a4b2-4ac5-b6bb-4b33cf81f804.png)

  
## Installation:

skinchanger:
1. Go to skinchanger/client/main.lua
2. Add this code
```lua
RegisterNetEvent('skinchanger:buyCloth')
AddEventHandler('skinchanger:buyCloth', function(data) 
	local shopData = json.decode(data)
	TriggerEvent('skinchanger:getSkin', function(skin)
		local characterData = skin
		characterData['torso_1'] = shopData.torso_1
		characterData['torso_2'] = shopData.torso_2
		characterData['tshirt_1'] = shopData.tshirt_1
		characterData['tshirt_2'] = shopData.tshirt_2
		characterData['arms'] = shopData.arms
		characterData['arms_2'] = shopData.arms_2
		characterData['decals_1'] = shopData.decals_1
		characterData['decals_2'] = shopData.decals_2
		characterData['pants_1'] = shopData.pants_1
		characterData['pants_2'] = shopData.pants_2
		characterData['shoes_1'] = shopData.shoes_1
		characterData['shoes_2'] = shopData.shoes_2
		characterData['mask_1'] = shopData.mask_1
		characterData['mask_2'] = shopData.mask_2
		characterData['bproof_1'] = shopData.bproof_1
		characterData['bproof_2'] = shopData.bproof_2
		characterData['chain_1'] = shopData.chain_1
		characterData['chain_2'] = shopData.chain_2
		characterData['bags_1'] = shopData.bags_1
		characterData['bags_2'] = shopData.bags_2
		characterData['helmet_1'] = shopData.helmet_1
		characterData['helmet_2'] = shopData.helmet_2
		characterData['glasses_1'] = shopData.glasses_1
		characterData['glasses_2'] = shopData.glasses_2
		characterData['watches_1'] = shopData.watches_1
		characterData['watches_2'] = shopData.watches_2
		characterData['bracelets_1'] = shopData.bracelets_1
		characterData['bracelets_2'] = shopData.bracelets_2
		characterData['ears_1'] = shopData.ears_1
		characterData['ears_2'] = shopData.ears_2
		ApplySkin(characterData)
		TriggerServerEvent('ECLIPSE:SaveData', json.encode(characterData))
	end)
end)
```
![image](https://user-images.githubusercontent.com/36680471/154804294-4b6e16cc-dc1c-4a91-b666-699dce15bb8f.png)

Start your server.

For more questions https://discord.gg/8nXR6rfB2C




