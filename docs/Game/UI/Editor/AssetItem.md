# Game.UI.Editor.AssetItem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.IItemPicker+Item`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `System.IComparable<Game.UI.Editor.AssetItem>`  

## Code

```csharp
public class AssetItem : Game.UI.Editor.IItemPicker+Item, Colossal.UI.Binding.IJsonWritable, System.IComparable<Game.UI.Editor.AssetItem>
{
    private Colossal.Hash128 <guid>k__BackingField;
    private System.String <fileName>k__BackingField;

    public Colossal.Hash128 guid { get; set; }
    public System.String fileName { get; set; }

    public AssetItem();

    public System.Int32 CompareTo(Game.UI.Editor.AssetItem other);
}
```


## Fields

- `private Colossal.Hash128 <guid>k__BackingField`  

```csharp
private Colossal.Hash128 <guid>k__BackingField;
```

- `private System.String <fileName>k__BackingField`  

```csharp
private System.String <fileName>k__BackingField;
```


## Properties

- `public Colossal.Hash128 guid { get; set }`  

```csharp
public Colossal.Hash128 guid { get; set; }
```

- `public System.String fileName { get; set }`  

```csharp
public System.String fileName { get; set; }
```


## Constructors

- `public AssetItem()`  

```csharp
public AssetItem();
```


## Methods

- `public CompareTo(Game.UI.Editor.AssetItem other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.UI.Editor.AssetItem other);
```


