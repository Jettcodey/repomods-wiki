# UI Elements Reference

All elements are created via `MenuAPI` factory methods. Most methods return a reference to a `REPOElement` script, allowing you to modify properties like text or color after creation.

## Buttons

`REPOButton` is the standard clickable component.

- **Method**: `MenuAPI.CreateREPOButton(text, onClick, parent, localPosition)`
- **Tip**: You can customize `labelTMP.color` or `labelTMP.fontSize` to change the button's appearance.

```csharp
var btn = MenuAPI.CreateREPOButton("Click Me", () => DoWork(), parent);
btn.labelTMP.color = Color.green;
```

## Toggles

`REPOToggle` provides an ON/OFF switch functionality.

- **Method**: `MenuAPI.CreateREPOToggle(text, onToggle, parent, localPosition, leftText, rightText, defaultValue)`

```csharp
MenuAPI.CreateREPOToggle("Feature Enabled", (isEnabled) => 
{
    myConfigValue = isEnabled;
}, parent, defaultValue: true);
```

## Sliders

`REPOSlider` supports floating point, integers, and fixed string options.

- **Bar Behavior**: Use `REPOSlider.BarBehavior` to control if the fill bar updates with the value or remains static.

### Option Slider
Useful for selecting from a list of predefined strings.

```csharp
string[] options = { "Option A", "Option B", "Option C" };
MenuAPI.CreateREPOSlider("Select Mode", "Description text here", (choice) => 
{
    Debug.Log($"Selected: {choice}");
}, parent, options, "Option A");
```

## Input Fields

`REPOInputField` allows users to type text directly into the menu.

```csharp
MenuAPI.CreateREPOInputField("Search", (text) => 
{
    currentFilter = text;
}, parent, placeholder: "Type here...");
```

## Visual Previews

You can render 3D avatars or game objects directly within your UI.

- **Avatar Preview**: `MenuAPI.CreateREPOAvatarPreview(parent, localPosition, enableBG, bgColor)`
- **Object Preview**: `MenuAPI.CreateREPOObjectPreview(parent, gameObject, localPosition, enableBG, bgColor)`

## Layout Helpers

- **Labels**: Standard text headers for organization.
- **Spacers**: Adds empty space to the layout. Use `new Vector2(width, height)` to define the gap size.