# Game.UI.Editor.UIIconField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IFieldBuilderFactory`  

## Code

```csharp
public class UIIconField : Game.UI.Widgets.IFieldBuilderFactory
{
    public UIIconField();

    public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
}
```


## Constructors

- `public UIIconField()`  

```csharp
public UIIconField();
```


## Methods

- `public TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public FieldBuilder TryCreate(Type memberType, object[] attributes)
	{
		return delegate(IValueAccessor accessor)
		{
			CastAccessor<string> castAccessor = new CastAccessor<string>(accessor);
			StringInputField stringInputField = new StringInputField
			{
				displayName = "URI",
				accessor = castAccessor
			};
			IconButton iconPicker = new IconButton
			{
				icon = ((accessor.GetValue() as string) ?? string.Empty)
			};
			iconPicker.action = delegate
			{
				World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<InspectorPanelSystem>().ShowThumbnailPicker(delegate(Colossal.Hash128 hash)
				{
					string text = string.Empty;
					if (AssetDatabase.global.TryGetAsset(hash, out ImageAsset asset))
					{
						text = asset.ToGlobalUri();
					}
					castAccessor.SetValue(text);
					iconPicker.icon = text;
				});
			};
			return new Group
			{
				displayName = "Icon",
				children = new IWidget[2] { stringInputField, iconPicker }
			};
		};
	}
```


## Nested types

- `Game.UI.Editor.UIIconField+<>c`  
- `Game.UI.Editor.UIIconField+<>c__DisplayClass0_0`  

