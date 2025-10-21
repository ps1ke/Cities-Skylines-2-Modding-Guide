# Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem>`  

## Code

```csharp
public sealed struct HierarchyItem : System.IComparable<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem>
{
    public Game.UI.Editor.EditorHierarchyUISystem+ItemId id;
    public System.Byte level;
    public System.Boolean expandable;
    public System.Boolean expanded;
    public System.Boolean selectable;

    public System.Int32 CompareTo(Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem other);
}
```


## Fields

- `public Game.UI.Editor.EditorHierarchyUISystem+ItemId id`  

```csharp
public Game.UI.Editor.EditorHierarchyUISystem+ItemId id;
```

- `public System.Byte level`  

```csharp
public System.Byte level;
```

- `public System.Boolean expandable`  

```csharp
public System.Boolean expandable;
```

- `public System.Boolean expanded`  

```csharp
public System.Boolean expanded;
```

- `public System.Boolean selectable`  

```csharp
public System.Boolean selectable;
```


## Methods

- `public CompareTo(Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem other);
```


