# MenuLib Overview

MenuLib is a programming API designed to simplify the creation and management of custom UI menus within R.E.P.O. It provides a standardized interface for injecting elements into existing game menus or creating standalone popup windows.

### Features
- **Extensive Menu Integration**: Inject custom elements into the Main Menu, Settings (Graphics, Audio, and Controls), Escape Menu, Lobby Menu, Color Menu, Region Selection, and Server List.
- **Standardized UI Elements**: Access pre-built components like Buttons, Toggles, Sliders (float, int, and string-options), and Input Fields that automatically match the game's aesthetic by utilizing original UI templates.
- **Custom Popup Pages**: Create entirely new scrollable menu pages featuring support for dimmers, custom headers, and automated layout management.
- **Event Handling**: Simplified hooks for button clicks, value changes, and text submission via standard C# Actions.

### Documentation Sections
- [Getting Started](./start.md): Installation and basic menu registration.
- [UI Elements](./elements.md): Detailed reference for standard UI components.
- [Custom Pages](./custom-pages.md): Guide for creating complex standalone popup menus.

### Quick Start
To use MenuLib in your project, ensure you have added the dependency to your `.csproj` as described in the [HarmonyX Project Setup](../../harmonyx.md#adding-thunderstore-dependencies).

## Resources
- [Thunderstore Page](https://thunderstore.io/c/repo/p/nickklmao/MenuLib/)
- [GitHub Repository](https://github.com/IsThatTheRealNick/MenuLib)