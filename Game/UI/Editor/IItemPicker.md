# Game.UI.Editor.IItemPicker

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IItemPicker
{
    public System.Int32 selectedIndex { get; set; }
    public System.Int32 visibleStartIndex { get; set; }
    public System.Int32 visibleEndIndex { get; set; }

    public abstract System.Void SetFavorite(System.Int32 index, System.Boolean favorite);
}
```


## Properties

- `public System.Int32 selectedIndex { get; set }`  

```csharp
public System.Int32 selectedIndex { get; set; }
```

- `public System.Int32 visibleStartIndex { get; set }`  

```csharp
public System.Int32 visibleStartIndex { get; set; }
```

- `public System.Int32 visibleEndIndex { get; set }`  

```csharp
public System.Int32 visibleEndIndex { get; set; }
```


## Methods

- `public abstract SetFavorite(System.Int32 index, System.Boolean favorite) : System.Void`  

```csharp
public abstract System.Void SetFavorite(System.Int32 index, System.Boolean favorite);
```


## Nested types

- `Game.UI.Editor.IItemPicker+Item`  
- `Game.UI.Editor.IItemPicker+Bindings`  

