# zCore
This read me is for mod dev.<br>
What exactly is zCore? zCore is a framework that let user has a mod setting UI in game.<br><br>


![image](https://user-images.githubusercontent.com/1011211/188297606-ef1492fb-b28c-4868-90bb-5e6942c1c8bd.png)<br><br><br>


## Instruction
1) Download zCore folder and put it in your `SandstormEditor\Insurgency\Plugins`
2) Go in Framework folder a right click `zCore_Modding_Base` and pick **create child blueprint class**
3) Move that blueprint class to your mod fold and put it in anywhere you want and call it whatever you want
4) Inside that child blueprint class, you will see the zCore section. Make sure you put your mod name and your mod version.<br><br>
![image](https://user-images.githubusercontent.com/1011211/188297785-18c129a3-2d35-4bb0-a7a1-929e2db64907.png)<br>
**Note:** Remember to change your mod version each time you uploaded your mod only with new settings. Otherwise the user will load up the old setting from previous version.<br><br>
5) Inside the **Settings**, you will add each setting in there. Make sure each setting has a name, description, and you setup correctly.
6) There some event you can call in this blueprint. These event is locate under the override button and it will fire when the user change their setting or load up the setting when join the game.<br><br>
![image](https://user-images.githubusercontent.com/1011211/188297898-f430e59f-ab3a-4a7b-a02d-329ada251caf.png)
7) Make sure you give this blueprint path to server owner so they can put it in the zCore mutator setting<br><br><br>


## Settings
![image](https://user-images.githubusercontent.com/1011211/188298097-1420cf1d-24b3-4af2-b3d0-429d6d42cbab.png)<br><br>
Each setting must have a name and a description. They will show up in the user UI.<br><br>

**ID**<br>
This is optional. It just special ID for your to keep track of your setting instead of using index<br><br>

**Type**<br>
There are 4 type of settings. Checkbox, Value, Dropdown, and keybind. You MUST pick 1 of these type.<br><br>

**Checkbox**<br>
If you are using checkbox type then set the default checkbox for the user. Only apply if user first time loading this setting.<br><br>

**Value**<br>
This will give user the slider with minimum value and maximum value. (Only apply if you are using value type)<br><br>

**Default Value**<br>
The default value for user first time loading it<br><br>

**DropDown List**<br>
A list for drop down. (Only apply if you are using dropdown type). You have 2 columns in here. The first column is the ID (Best to make it unique and no space). This ID is only for you to identify what user pick. The 2nd column is the name that will show up in the user UI setting when they click on the drop down list.<br>
**Note:** Case sensitive<br><br>

**Default DropDown ID**<br>
This is the default ID that the user first time loading this setting. The ID must be the same as the dropdown list you put above.<br>
**Note:** Case sensitive<br><br>

**Keybind**<br>
This only apply if your setting type is keybind. Make sure you have the binding name and description. Action Mapping is what the input key call (Make sure this is really unique and best to have no space so it won't have conflict with other mod). There is no default keybind for user so user will have to bind it themselves.<br><br>

**Default Key**<br>
The default key for this keybind.<br><br><br>


## Server and Client
Your zCore is spawn on server. It basically run on both server and client. However, all zCore event will be run on client only except **OnServerExecuted** event.<br><br>
![9qFP7LlhnZ](https://user-images.githubusercontent.com/1011211/188524841-4c9f0238-b885-43b0-9263-6bb049342332.png)<br><br>

This event will fire when you call this function.<br><br>
![image](https://user-images.githubusercontent.com/1011211/188524986-48435b37-3e53-4aec-a71a-4ab1f0cc2568.png)<br><br>

Beware, only use this function when you want the server to do something. It can affect the entire map and gameplay
