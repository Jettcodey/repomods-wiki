# Registering Shop Items with REPOLib

::: info NOTE
This page assumes you have a Harmony project setup for R.E.P.O. modding.\
If not, first follow the guide in [Harmony Project Setup](../../harmonyx.md).
:::

Registering an item:

```c#
private void Awake()
{
    REPOLib.BundleLoader.LoadBundle("your_assetbundle_file_path", assetBundle => 
    {
        var item = assetBundle.LoadAsset<Item>("your_item");
        REPOLib.Modules.Items.RegisterItem(item);
    });
}
```
