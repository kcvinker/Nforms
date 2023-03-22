
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


