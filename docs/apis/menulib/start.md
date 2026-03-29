# Getting Started with MenuLib

MenuLib utilizes a registration system based on delegates to ensure that UI elements are instantiated at the correct moment when the game's menus are being initialized. This ensures your components are correctly parented and match the game's layout.

## Registration Hooks

To inject elements into the game, you must register a `BuilderDelegate` with one of the static methods in `MenuAPI`. The delegate provides a `Transform parent`, which is the container where your elements should be placed.

| Hook Method | Target Menu |
| --- | --- |
| `AddElementToMainMenu` | The main title screen. |
| `AddElementToSettingsMenu` | The standard settings menu. |
| `AddElementToEscapeMenu` | The in-game pause menu. |
| `AddElementToLobbyMenu` | The multiplayer lobby screen. |
| `AddElementToColorMenu` | The character color selection menu. |
| `AddElementToRegionSelectionMenu` | The region picker menu. |
| `AddElementToServerListMenu` | The public server browser. |

## Basic Implementation

In your mod's initialization (e.g., `Awake`), register your building method. Use generic offsets to position buttons within the game's existing layouts.

```csharp
using MenuLib;
using UnityEngine;

namespace MyMod;

public class MyModPlugin : BepInEx.BaseUnityPlugin
{
    private void Awake()
    {
        // 1. Register your builder during Awake
        MenuAPI.AddElementToMainMenu(BuildMyMenu);
    }

    private void BuildMyMenu(Transform parent)
    {
        // 2. Create a button with a specific offset to avoid overlapping game buttons
        MenuAPI.CreateREPOButton("My Mod Menu", () => 
        {
            Debug.Log("Button clicked!");
        }, parent, new Vector2(550f, 22f));
    }
}
```

## Interactive Popups

You can trigger a standard two-option confirmation popup (Yes/No style) directly from `MenuAPI`.

```csharp
MenuAPI.OpenPopup(
    "Warning", 
    Color.red, 
    "This action cannot be undone. Proceed?", 
    () => { /* Logic for Yes */ }, 
    () => { /* Logic for No */ }
);
```