# Game.UI.Widgets.ListAdapter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.ListAdapterBase<System.Collections.IList>`  
**Implements:** `Game.UI.Widgets.IListAdapter`  

## Code

```csharp
public class ListAdapter : Game.UI.Widgets.ListAdapterBase<System.Collections.IList>, Game.UI.Widgets.IListAdapter
{
    private System.Type <listType>k__BackingField;

    public System.Type listType { get; set; }

    public ListAdapter();

    public virtual System.Void Clear();
    public virtual System.Void DeleteElement(System.Int32 index);
    public static Game.UI.Widgets.ListAdapter FromList<T>(System.Collections.Generic.List<T> list, Game.UI.Widgets.IEditorGenerator generator);
    public virtual System.Void InsertElement(System.Int32 index);
}
```


## Fields

- `private System.Type <listType>k__BackingField`  

```csharp
private System.Type <listType>k__BackingField;
```


## Properties

- `public System.Type listType { get; set }`  

```csharp
public System.Type listType { get; set; }
```


## Constructors

- `public ListAdapter()`  

```csharp
public ListAdapter();
```


## Methods

- `public virtual Clear() : System.Void`  

```csharp
public virtual System.Void Clear();
```

- `public virtual DeleteElement(System.Int32 index) : System.Void`  

```csharp
public virtual System.Void DeleteElement(System.Int32 index);
```

- `public static FromList<T>(System.Collections.Generic.List<T> list, Game.UI.Widgets.IEditorGenerator generator) : Game.UI.Widgets.ListAdapter`  

```csharp
public static Game.UI.Widgets.ListAdapter FromList<T>(System.Collections.Generic.List<T> list, Game.UI.Widgets.IEditorGenerator generator);
```

- `public virtual InsertElement(System.Int32 index) : System.Void`  

```csharp
public virtual System.Void InsertElement(System.Int32 index);
```


## Nested types

- `Game.UI.Widgets.ListAdapter+<>c__DisplayClass7_0<T>`  

