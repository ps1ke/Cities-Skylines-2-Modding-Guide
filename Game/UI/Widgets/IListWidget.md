# Game.UI.Widgets.IListWidget

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** interface abstract public  

**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public abstract interface IListWidget : Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable
{
    public abstract System.Int32 AddElement();
    public abstract System.Void Clear();
    public abstract System.Void DeleteElement(System.Int32 index);
    public abstract System.Int32 DuplicateElement(System.Int32 index);
    public abstract System.Void InsertElement(System.Int32 index);
    public abstract System.Void MoveElement(System.Int32 fromIndex, System.Int32 toIndex);
}
```


## Methods

- `public abstract AddElement() : System.Int32`  

```csharp
public abstract System.Int32 AddElement();
```

- `public abstract Clear() : System.Void`  

```csharp
public abstract System.Void Clear();
```

- `public abstract DeleteElement(System.Int32 index) : System.Void`  

```csharp
public abstract System.Void DeleteElement(System.Int32 index);
```

- `public abstract DuplicateElement(System.Int32 index) : System.Int32`  

```csharp
public abstract System.Int32 DuplicateElement(System.Int32 index);
```

- `public abstract InsertElement(System.Int32 index) : System.Void`  

```csharp
public abstract System.Void InsertElement(System.Int32 index);
```

- `public abstract MoveElement(System.Int32 fromIndex, System.Int32 toIndex) : System.Void`  

```csharp
public abstract System.Void MoveElement(System.Int32 fromIndex, System.Int32 toIndex);
```


