## Supported Elements
- Window  
- Tab  
- Toggle  
- Button  
- Slider  
- Dropdown  
- Divider  
- Label  

## Load Library
```lua
local Bracket = loadstring(game:HttpGet("https://raw.githubusercontent.com/AlexR32/Bracket/refs/heads/main/BracketV34.lua"))()
```

## Basic Usage

### Create Window
```lua
local Window = Bracket:Window({
    Name = "My Script Hub",
    Enabled = true,
    Color = Color3.fromRGB(255, 255, 255),
    Size = UDim2.fromOffset(380, 240),
    Position = UDim2.new(0.5, -240, 0.5, -160)
})
```

### Create Tabs
```lua
local Tabs = {
    Main = Window:Tab({Name = "Main"}),
    Settings = Window:Tab({Name = "Settings"}),
    Credits = Window:Tab({Name = "Credits"})
}
```

### Add Elements

#### Toggle
```lua
Tabs.Main:Toggle({
    Name = "Enable Feature",
    Value = false,
    Callback = function(value)
        print("Toggle state:", value)
    end
})
```

#### Button
```lua
Tabs.Main:Button({
    Name = "Click Me",
    Callback = function()
        print("Button clicked!")
    end
})
```

#### Slider
```lua
Tabs.Main:Slider({
    Name = "Speed",
    Min = 0,
    Max = 100,
    Value = 50,
    Callback = function(value)
        print("Slider value:", value)
    end
})
```

#### Dropdown
```lua
Tabs.Main:Dropdown({
    Name = "Select Option",
    Default = {"Option 1"},
    List = {
        {
            Name = "Option 1",
            Mode = "Button",
            Callback = function()
                print("Option 1 selected")
            end
        },
        {
            Name = "Option 2",
            Mode = "Button",
            Callback = function()
                print("Option 2 selected")
            end
        }
    }
})
```

#### Divider
```lua
Tabs.Main:Divider({Text = "Section Name"})
```

#### Label
```lua
Tabs.Main:Label({Text = "This is a label"})
```

#### Keybind
```lua
Tabs.Settings:Keybind({
    Name = "Toggle UI",
    Key = "RightShift",
    Callback = function(key)
        Bracket:Toggle()
    end
})
```

#### Colorpicker
```lua
Tabs.Settings:Colorpicker({
    Name = "UI Color",
    Color = Color3.fromRGB(255, 255, 255),
    Callback = function(color)
        print("Color changed:", color)
    end
})
```

## Example
```lua
local Bracket = loadstring(game:HttpGet("https://raw.githubusercontent.com/AlexR32/Bracket/refs/heads/main/BracketV34.lua"))()

local Window = Bracket:Window({
    Name = "Example Hub",
    Enabled = true,
    Color = Color3.fromRGB(255, 255, 255),
    Size = UDim2.fromOffset(380, 240),
    Position = UDim2.new(0.5, -240, 0.5, -160)
})

local Tabs = {
    Main = Window:Tab({Name = "Main"}),
    Settings = Window:Tab({Name = "Settings"})
}

Tabs.Main:Divider({Text = "Features"})

Tabs.Main:Toggle({
    Name = "Farm",
    Value = false,
    Callback = function(value)
        print("Farm:", value)
    end
})

Tabs.Main:Slider({
    Name = "Farm Speed",
    Min = 1,
    Max = 10,
    Value = 5,
    Callback = function(value)
        print("Speed:", value)
    end
})

