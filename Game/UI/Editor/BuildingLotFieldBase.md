# Game.UI.Editor.BuildingLotFieldBase

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IFieldBuilderFactory`  

## Code

```csharp
public abstract class BuildingLotFieldBase : Game.UI.Widgets.IFieldBuilderFactory
{
    private static readonly System.Int32 kMaxSize;
    private static readonly System.Int32 kMinSize;

    protected BuildingLotFieldBase();

    private static System.Void AddCells(Game.Prefabs.BuildingPrefab prefab, Game.UI.Widgets.IWidget widget, Unity.Mathematics.int2 dir, System.Int32 count);
    public abstract Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
    protected Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes, System.Boolean horizontal);
    private static System.Boolean TryGetBuildingPrefab(Game.Reflection.IValueAccessor accessor, Game.Prefabs.BuildingPrefab& prefab);
}
```


## Fields

- `private static readonly System.Int32 kMaxSize`  

```csharp
private static readonly System.Int32 kMaxSize;
```

- `private static readonly System.Int32 kMinSize`  

```csharp
private static readonly System.Int32 kMinSize;
```


## Constructors

- `protected BuildingLotFieldBase()`  

```csharp
protected BuildingLotFieldBase();
```


## Methods

- `private static AddCells(Game.Prefabs.BuildingPrefab prefab, Game.UI.Widgets.IWidget widget, Unity.Mathematics.int2 dir, System.Int32 count = 1) : System.Void`  

```csharp
private static System.Void AddCells(Game.Prefabs.BuildingPrefab prefab, Game.UI.Widgets.IWidget widget, Unity.Mathematics.int2 dir, System.Int32 count);
```

- `public abstract TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public abstract Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
```

- `protected TryCreate(System.Type memberType, System.Object[] attributes, System.Boolean horizontal) : Game.UI.Widgets.FieldBuilder`  

```csharp
protected Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes, System.Boolean horizontal);
```

- `private static TryGetBuildingPrefab(Game.Reflection.IValueAccessor accessor, Game.Prefabs.BuildingPrefab& prefab) : System.Boolean`  

```csharp
private static System.Boolean TryGetBuildingPrefab(Game.Reflection.IValueAccessor accessor, Game.Prefabs.BuildingPrefab& prefab);
```


## Nested types

- `Game.UI.Editor.BuildingLotFieldBase+<>c`  
- `Game.UI.Editor.BuildingLotFieldBase+<>c__DisplayClass3_0`  
- `Game.UI.Editor.BuildingLotFieldBase+<>c__DisplayClass3_1`  
- `Game.UI.Editor.BuildingLotFieldBase+<>c__DisplayClass3_2`  

