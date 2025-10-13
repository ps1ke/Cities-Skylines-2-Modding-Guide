# Game.UI.Menu.ModdingToolchainSettingItem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.Menu.AutomaticSettings+SettingItemData`  

## Code

```csharp
public class ModdingToolchainSettingItem : Game.UI.Menu.AutomaticSettings+SettingItemData
{
    private readonly System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingItemData> <children>k__BackingField;

    public System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingItemData> children { get; }

    public ModdingToolchainSettingItem(Game.Settings.Setting setting, Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String prefix);

    private Game.Modding.Toolchain.IToolchainDependency <GetWidget>b__4_0();
    protected virtual Game.UI.Widgets.IWidget GetWidget();
}
```


## Fields

- `private readonly System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingItemData> <children>k__BackingField`  

```csharp
private readonly System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingItemData> <children>k__BackingField;
```


## Properties

- `public System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingItemData> children { get }`  

```csharp
public System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingItemData> children { get; }
```


## Constructors

- `public ModdingToolchainSettingItem(Game.Settings.Setting setting, Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String prefix)`  

```csharp
public ModdingToolchainSettingItem(Game.Settings.Setting setting, Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String prefix);
```


## Methods

- `private <GetWidget>b__4_0() : Game.Modding.Toolchain.IToolchainDependency`  

```csharp
private Game.Modding.Toolchain.IToolchainDependency <GetWidget>b__4_0();
```

- `protected virtual GetWidget() : Game.UI.Widgets.IWidget`  

```csharp
protected override IWidget GetWidget()
	{
		return new ModdingToolchainDependency
		{
			path = base.path,
			displayName = base.displayName,
			description = base.description,
			displayNameAction = base.dispayNameAction,
			descriptionAction = base.descriptionAction,
			accessor = new DelegateAccessor<IToolchainDependency>(() => (IToolchainDependency)base.property.GetValue(base.setting)),
			valueVersion = base.valueVersionAction,
			disabled = base.disableAction,
			hidden = base.hideAction,
			children = (from c in children
				select c.widget into w
				where w != null
				select w).ToArray()
		};
	}
```


## Nested types

- `Game.UI.Menu.ModdingToolchainSettingItem+<>c`  

