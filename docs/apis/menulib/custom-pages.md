# Custom Popup Pages

`REPOPopupPage` provides a standalone, scrollable window. These are ideal for complex mod configurations that require more space than a single button can provide.

## Creating and Opening Pages

When creating a page, you define its side and whether it should be cached in memory.

```csharp
// Parameters: Header, ShouldCache, DimmerVisibility, Spacing, LocalPosition
var myPage = MenuAPI.CreateREPOPopupPage("Mod Settings", true, true, 2f);

// To open the page:
myPage.OpenPage(false);
```

## Adding Elements

### 1. Scrollable Content
Elements added to the Scroll View are automatically stacked vertically. The builder delegate **must** return the `RectTransform` of the element.

```csharp
myPage.AddElementToScrollView((scroller) => 
{
    var toggle = MenuAPI.CreateREPOToggle("Sub Option", (val) => {}, scroller);
    return toggle.rectTransform; 
}, topPadding: 5f, bottomPadding: 5f);
```

### 2. Static Content
Use `AddElement` for elements that should stay fixed (like a "Back" button at the bottom) and not scroll with the rest of the content.

```csharp
myPage.AddElement((parent) => 
{
    MenuAPI.CreateREPOButton("Back", () => myPage.ClosePage(true), parent, new Vector2(77f, 20f));
});
```

## Advanced Stacking & Layouts

### Side-by-Side Pages
A common pattern is opening a category menu on the **Left** and a detailed selection menu on the **Right**.

```csharp
// Create a detail page on the right side
var detailPage = MenuAPI.CreateREPOPopupPage("Details", REPOPopupPage.PresetSide.Right, false);

// Open it "on top" of the current left-side page
detailPage.OpenPage(true);
```

### Managing Stacked Pages
If you are opening multiple pages on top of each other, you can clear the stack using:
```csharp
MenuAPI.CloseAllPagesAddedOnTop();
```

## Customizing Visuals

You can adjust the scroll view padding and dimmer settings to fit your mod's theme.

```csharp
myPage.pageDimmerOpacity = 0.5f;
// Adjust internal mask padding (Left, Top, Right, Bottom)
myPage.maskPadding = new Padding(10, 10, 10, 25);
```