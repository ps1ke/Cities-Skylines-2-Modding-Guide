# Game.UI.Widgets.IListAdapter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IListAdapter
{
    public System.Int32 length { get; }
    public System.Boolean resizable { get; }
    public System.Boolean sortable { get; }

    public abstract System.Int32 AddElement();
    public abstract System.Collections.Generic.IEnumerable<Game.UI.Widgets.IWidget> BuildElementsInRange();
    public abstract System.Void Clear();
    public abstract System.Void DeleteElement(System.Int32 index);
    public abstract System.Int32 DuplicateElement(System.Int32 index);
    public abstract System.Void InsertElement(System.Int32 index);
    public abstract System.Void MoveElement(System.Int32 fromIndex, System.Int32 toIndex);
    public abstract System.Boolean UpdateRange(System.Int32 startIndex, System.Int32 endIndex);
}
```


## Properties

- `public System.Int32 length { get }`  

```csharp
public System.Int32 length { get; }
```

- `public System.Boolean resizable { get }`  

```csharp
public System.Boolean resizable { get; }
```

- `public System.Boolean sortable { get }`  

```csharp
public System.Boolean sortable { get; }
```


## Methods

- `public abstract AddElement() : System.Int32`  

```csharp
public abstract System.Int32 AddElement();
```

- `public abstract BuildElementsInRange() : System.Collections.Generic.IEnumerable<Game.UI.Widgets.IWidget>`  

```csharp
public abstract System.Collections.Generic.IEnumerable<Game.UI.Widgets.IWidget> BuildElementsInRange();
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

- `public abstract UpdateRange(System.Int32 startIndex, System.Int32 endIndex) : System.Boolean`  

```csharp
public abstract System.Boolean UpdateRange(System.Int32 startIndex, System.Int32 endIndex);
```


