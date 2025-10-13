# Game.UI.Widgets.MultilineTextSettingItemData

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Menu.AutomaticSettings+SettingItemData`  

## Code

```csharp
public class MultilineTextSettingItemData : Game.UI.Menu.AutomaticSettings+SettingItemData
{
    private System.String <icon>k__BackingField;

    public System.String icon { get; set; }

    public MultilineTextSettingItemData(Game.Settings.Setting setting, Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String prefix);

    protected virtual Game.UI.Widgets.IWidget GetWidget();
}
```


## Fields

- `private System.String <icon>k__BackingField`  

```csharp
private System.String <icon>k__BackingField;
```


## Properties

- `public System.String icon { get; set }`  

```csharp
public System.String icon { get; set; }
```


## Constructors

- `public MultilineTextSettingItemData(Game.Settings.Setting setting, Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String prefix)`  

```csharp
public MultilineTextSettingItemData(Game.Settings.Setting setting, Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String prefix);
```


## Methods

- `protected virtual GetWidget() : Game.UI.Widgets.IWidget`  

```csharp
protected override IWidget GetWidget()
	{
		return new MultilineText
		{
			path = base.path,
			displayName = base.displayName,
			displayNameAction = base.dispayNameAction,
			icon = icon,
			hidden = base.hideAction,
			disabled = base.disableAction
		};
	}
```


