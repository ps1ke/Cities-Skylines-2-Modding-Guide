# Game.Serialization.PrefabReferences

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct PrefabReferences
{
    private Unity.Entities.ComponentLookup<Game.Prefabs.PrefabData> m_PrefabData;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_PrefabArray;
    private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> m_ReferencedPrefabs;
    private Unity.Entities.Entity m_LastPrefabIn;
    private Unity.Entities.Entity m_LastPrefabOut;
    private System.Boolean m_IsLoading;

    public PrefabReferences(Unity.Collections.NativeArray<Unity.Entities.Entity> prefabArray, Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> referencedPrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabData> prefabData, System.Boolean isLoading);

    public System.Void Check(Unity.Entities.Entity& prefab);
    public Unity.Entities.Entity Check(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity prefab);
    public System.Void SetDirty(Unity.Entities.Entity prefab);
}
```


## Fields

- `private Unity.Entities.ComponentLookup<Game.Prefabs.PrefabData> m_PrefabData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.PrefabData> m_PrefabData;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_PrefabArray`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_PrefabArray;
```

- `private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> m_ReferencedPrefabs`  

```csharp
private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> m_ReferencedPrefabs;
```

- `private Unity.Entities.Entity m_LastPrefabIn`  

```csharp
private Unity.Entities.Entity m_LastPrefabIn;
```

- `private Unity.Entities.Entity m_LastPrefabOut`  

```csharp
private Unity.Entities.Entity m_LastPrefabOut;
```

- `private System.Boolean m_IsLoading`  

```csharp
private System.Boolean m_IsLoading;
```


## Constructors

- `public PrefabReferences(Unity.Collections.NativeArray<Unity.Entities.Entity> prefabArray, Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> referencedPrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabData> prefabData, System.Boolean isLoading)`  

```csharp
public PrefabReferences(Unity.Collections.NativeArray<Unity.Entities.Entity> prefabArray, Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> referencedPrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabData> prefabData, System.Boolean isLoading);
```


## Methods

- `public Check(Unity.Entities.Entity& prefab) : System.Void`  

```csharp
public System.Void Check(Unity.Entities.Entity& prefab);
```

- `public Check(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity prefab) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity Check(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity prefab);
```

- `public SetDirty(Unity.Entities.Entity prefab) : System.Void`  

```csharp
public System.Void SetDirty(Unity.Entities.Entity prefab);
```


