
# Nforms GUI Library for Windows
## A simple GUI library for Nelua programming language. Based on Windows API

## Screenshots
![image](https://user-images.githubusercontent.com/8840907/222894006-93484f7a-3231-40d4-afd5-1c4ca9fef20b.png)


## Code for the above screenshot
```ts

require "nforms"

local frm = Form.new("NForms GUI Library")
f:createHandle()

local b = Button.new(&frm, "Normal Btn")
b:createHandle()

local b2 = Button.new(&frm, "Flat Btn", 170)
b2:setBackColor(0xfdc500)
b2:createHandle()

local b3 = Button.new(&frm, "Gradient Btn", 320)
b3:setGradientColor(0xeeef20, 0x70e000)
b3:createHandle()

local function btnClick(bn: pointer, e: *EventArgs)
	local bt = (@*Button)(bn) // Normally we don't need this here. Just for displaying the feature.
	print("btn clicked ", bt.text)
end  
b.onClick = &btnClick // Connect click event to button

frm:show()

```

## Screenshot 

![image](https://user-images.githubusercontent.com/8840907/227059551-662c51a7-ed4a-4b1b-88e9-a1fc87c755e4.png)


## Code for this image

```ts
require "nforms"

local f = Form.new("NForms GUI Library", 800)
f:createHandle()

local b = Button.new(&f, "Normal Btn")
b:createHandle()

local b2 = Button.new(&f, "Flat Btn", 170)
b2:setBackColor(0xfdc500)
b2:createHandle()

local b3 = Button.new(&f, "Gradient Btn", 320)
b3:setGradientColor(0xeeef20, 0x70e000)
b3:createHandle()

local tb = TextBox.new(&f, "Text Box", 20, 65)
tb:createHandle()

local lb = Label.new(&f, "Static Label", 172, 70)
lb:createHandle()

local cb = CheckBox.new(&f, "CheckBox", 275, 70)
-- cb:setBackColor(0xffbf69)
-- cb:setForeColor(0xffffff)
cb:createHandle()

local rb = RadioButton.new(&f, "Radio 1", 20, 110)
rb:createHandle()
local rb2 = RadioButton.new(&f, "Radio 2", 20, 140)
rb2:setForeColor(0xf94144)
rb2:createHandle()

local cmb = ComboBox.new(&f, 20, 320)
cmb:addItem("Sample")
cmb:createHandle()

local lbx = ListBox.new(&f, 20, 172)
lbx:addItems("Windows", "MacOS", "Linux")
lbx:createHandle()


local dtp = DateTimePicker.new(&f, 116, 114)
dtp:createHandle()

local gb = GroupBox.new(&f, "", 182, 170)
gb:createHandle()

local np = NumberPicker.new(&f, 182, 280)
np.step = 0.5
np:createHandle()

local np2 = NumberPicker.new(&f, 182, 320)
np2:createHandle()

local tk = TrackBar.new(&f, 253, 110)
tk.customDraw = true
-- tk.selectionRange = true
tk:createHandle()

local tv = TreeView.new(&f, 325, 160)
tv:createHandle()
local tnWIn = tv:addNode("Windows")
local tnLin = tv:addNode("Linux")
local tnRe = tv:addNode("ReactOS")

tv:addChildNode("Win7", tnWIn)
tv:addChildNode("Win8", tnWIn)
tv:addChildNode("Win10", tnWIn)
tv:addChildNode("Ubuntu", tnLin)
tv:addChildNode("Mint", tnLin)

local lv = ListView.new(&f, 485, 20)
lv:createHandle()
-- lv:addColumn("Names", 80)
-- lv:addColumn("Job", 100)
lv:addColumns({"Names", "Jobs", "Salaries"}, {80, 100, 80})
lv:addRows("Paul", "Translator", 45000)
lv:addRows("Sam", "Accountabt", 15000)
lv:addRows("Jerome", "Clerk", 9000)
f:show()
```
