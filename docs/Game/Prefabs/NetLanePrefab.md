# Game.Prefabs.NetLanePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class NetLanePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.PathfindPrefab m_PathfindPrefab;

    public NetLanePrefab();

    private Unity.Entities.EntityArchetype CreateArchetype(Unity.Entities.EntityManager entityManager, System.Collections.Generic.List<Game.Prefabs.ComponentBase> unityComponents, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> laneComponents);
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PathfindPrefab m_PathfindPrefab`  

```csharp
public Game.Prefabs.PathfindPrefab m_PathfindPrefab;
```


## Constructors

- `public NetLanePrefab()`  

```csharp
public NetLanePrefab();
```


## Methods

- `private CreateArchetype(Unity.Entities.EntityManager entityManager, System.Collections.Generic.List<Game.Prefabs.ComponentBase> unityComponents, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> laneComponents) : Unity.Entities.EntityArchetype`  

```csharp
private Unity.Entities.EntityArchetype CreateArchetype(Unity.Entities.EntityManager entityManager, System.Collections.Generic.List<Game.Prefabs.ComponentBase> unityComponents, System.Collections.Generic.HashSet<Unity.Entities.ComponentType> laneComponents);
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


