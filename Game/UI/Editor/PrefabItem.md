# Game.UI.Editor.PrefabItem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.IItemPicker+Item`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `System.IComparable<Game.UI.Editor.PrefabItem>`  

## Code

```csharp
public class PrefabItem : Game.UI.Editor.IItemPicker+Item, Colossal.UI.Binding.IJsonWritable, System.IComparable<Game.UI.Editor.PrefabItem>
{
    private Game.Prefabs.PrefabBase <prefab>k__BackingField;
    private System.Collections.Generic.List<System.String> <tags>k__BackingField;

    public Game.Prefabs.PrefabBase prefab { get; set; }
    public System.Collections.Generic.List<System.String> tags { get; set; }

    public PrefabItem();

    public System.Int32 CompareTo(Game.UI.Editor.PrefabItem other);
}
```


## Fields

- `private Game.Prefabs.PrefabBase <prefab>k__BackingField`  

```csharp
private Game.Prefabs.PrefabBase <prefab>k__BackingField;
```

- `private System.Collections.Generic.List<System.String> <tags>k__BackingField`  

```csharp
private System.Collections.Generic.List<System.String> <tags>k__BackingField;
```


## Properties

- `public Game.Prefabs.PrefabBase prefab { get; set }`  

```csharp
public Game.Prefabs.PrefabBase prefab { get; set; }
```

- `public System.Collections.Generic.List<System.String> tags { get; set }`  

```csharp
public System.Collections.Generic.List<System.String> tags { get; set; }
```


## Constructors

- `public PrefabItem()`  

```csharp
public PrefabItem();
```


## Methods

- `public CompareTo(Game.UI.Editor.PrefabItem other) : System.Int32`  

```csharp
public int CompareTo(PrefabItem other)
	{
		if (base.favorite == other.favorite)
		{
			return string.CompareOrdinal(prefab?.name, other.prefab?.name);
		}
		return -base.favorite.CompareTo(other.favorite);
	}
```


