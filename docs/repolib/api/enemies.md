# Registering Enemies with REPOLib

::: info NOTE
This page assumes you have a Harmony project setup for R.E.P.O. modding.\
If not, first follow the guide in [Harmony Project Setup](../../harmonyx.md).
:::

Registering an enemy:

```c#
private void Awake()
{
    REPOLib.BundleLoader.LoadBundle("your_assetbundle_file_path", assetBundle => 
    {
        var enemySetup = assetBundle.LoadAsset<EnemySetup>("your_enemy_setup");
        REPOLib.Modules.Enemies.RegisterEnemy(enemySetup);
    });
}
```
