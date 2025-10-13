# Game.UI.UIObjectInfo

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.UI.UIObjectInfo>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct UIObjectInfo : System.IComparable<Game.UI.UIObjectInfo>
{
    private readonly Unity.Entities.Entity <entity>k__BackingField;
    private readonly Game.Prefabs.PrefabData <prefabData>k__BackingField;
    private readonly System.Int32 <priority>k__BackingField;

    public Unity.Entities.Entity entity { get; }
    public Game.Prefabs.PrefabData prefabData { get; }
    public System.Int32 priority { get; }

    public UIObjectInfo(Unity.Entities.Entity entity, System.Int32 priority);
    public UIObjectInfo(Unity.Entities.Entity entity, Game.Prefabs.PrefabData prefabData, System.Int32 priority);

    public System.Int32 CompareTo(Game.UI.UIObjectInfo other);
    public static Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetObjects(Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> elements, Unity.Collections.Allocator allocator);
    public static Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedObjects(Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator);
    public static Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedObjects(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator);
    public static Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedObjects(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeList<Unity.Entities.Entity> entities, Unity.Collections.Allocator allocator);
    public static Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedObjects(Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> elements, Unity.Collections.Allocator allocator);
}
```


## Fields

- `private readonly Unity.Entities.Entity <entity>k__BackingField`  

```csharp
private readonly Unity.Entities.Entity <entity>k__BackingField;
```

- `private readonly Game.Prefabs.PrefabData <prefabData>k__BackingField`  

```csharp
private readonly Game.Prefabs.PrefabData <prefabData>k__BackingField;
```

- `private readonly System.Int32 <priority>k__BackingField`  

```csharp
private readonly System.Int32 <priority>k__BackingField;
```


## Properties

- `public Unity.Entities.Entity entity { get }`  

```csharp
public Unity.Entities.Entity entity { get; }
```

- `public Game.Prefabs.PrefabData prefabData { get }`  

```csharp
public Game.Prefabs.PrefabData prefabData { get; }
```

- `public System.Int32 priority { get }`  

```csharp
public System.Int32 priority { get; }
```


## Constructors

- `public UIObjectInfo(Unity.Entities.Entity entity, System.Int32 priority)`  

```csharp
public UIObjectInfo(Unity.Entities.Entity entity, System.Int32 priority);
```

- `public UIObjectInfo(Unity.Entities.Entity entity, Game.Prefabs.PrefabData prefabData, System.Int32 priority)`  

```csharp
public UIObjectInfo(Unity.Entities.Entity entity, Game.Prefabs.PrefabData prefabData, System.Int32 priority);
```


## Methods

- `public CompareTo(Game.UI.UIObjectInfo other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.UI.UIObjectInfo other);
```

- `public static GetObjects(Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> elements, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

```csharp
public static Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetObjects(Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> elements, Unity.Collections.Allocator allocator);
```

- `public static GetSortedObjects(Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

```csharp
public static Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedObjects(Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator);
```

- `public static GetSortedObjects(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

```csharp
public static Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedObjects(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator);
```

- `public static GetSortedObjects(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeList<Unity.Entities.Entity> entities, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

```csharp
public static Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedObjects(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeList<Unity.Entities.Entity> entities, Unity.Collections.Allocator allocator);
```

- `public static GetSortedObjects(Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> elements, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

```csharp
public static Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedObjects(Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> elements, Unity.Collections.Allocator allocator);
```


