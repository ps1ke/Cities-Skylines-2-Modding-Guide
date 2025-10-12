# Game.UI.UIObjectInfo

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.UI.UIObjectInfo>`  

**Attributes:** `IsReadOnly`  

## Fields

- `private readonly Unity.Entities.Entity <entity>k__BackingField`  
- `private readonly Game.Prefabs.PrefabData <prefabData>k__BackingField`  
- `private readonly System.Int32 <priority>k__BackingField`  

## Properties

- `public Unity.Entities.Entity entity { get }`  
- `public Game.Prefabs.PrefabData prefabData { get }`  
- `public System.Int32 priority { get }`  

## Constructors

- `public UIObjectInfo(Unity.Entities.Entity entity, System.Int32 priority)`  
- `public UIObjectInfo(Unity.Entities.Entity entity, Game.Prefabs.PrefabData prefabData, System.Int32 priority)`  

## Methods

- `public CompareTo(Game.UI.UIObjectInfo other) : System.Int32`  
- `public static GetObjects(Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> elements, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  
- `public static GetSortedObjects(Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  
- `public static GetSortedObjects(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  
- `public static GetSortedObjects(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeList<Unity.Entities.Entity> entities, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  
- `public static GetSortedObjects(Unity.Entities.EntityManager entityManager, Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> elements, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

