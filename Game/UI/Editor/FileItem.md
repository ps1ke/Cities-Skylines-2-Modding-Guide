# Game.UI.Editor.FileItem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.IItemPicker+Item`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `System.IComparable<Game.UI.Editor.FileItem>`  

## Code

```csharp
public class FileItem : Game.UI.Editor.IItemPicker+Item, Colossal.UI.Binding.IJsonWritable, System.IComparable<Game.UI.Editor.FileItem>
{
    private System.String <path>k__BackingField;

    public System.String path { get; set; }

    public FileItem();

    public System.Int32 CompareTo(Game.UI.Editor.FileItem other);
}
```


## Fields

- `private System.String <path>k__BackingField`  

```csharp
private System.String <path>k__BackingField;
```


## Properties

- `public System.String path { get; set }`  

```csharp
public System.String path { get; set; }
```


## Constructors

- `public FileItem()`  

```csharp
public FileItem();
```


## Methods

- `public CompareTo(Game.UI.Editor.FileItem other) : System.Int32`  

```csharp
public int CompareTo(FileItem other)
	{
		return string.CompareOrdinal(path, other.path);
	}
```


