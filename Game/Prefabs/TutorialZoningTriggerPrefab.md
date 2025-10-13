# Game.Prefabs.TutorialZoningTriggerPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TutorialTriggerPrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TutorialZoningTriggerPrefab : Game.Prefabs.TutorialTriggerPrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.ZonePrefab[] m_Zones;

    public TutorialZoningTriggerPrefab();

    protected virtual System.Void GenerateBlinkTags();
    public virtual System.Void GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.ZonePrefab[] m_Zones`  

```csharp
public Game.Prefabs.ZonePrefab[] m_Zones;
```


## Constructors

- `public TutorialZoningTriggerPrefab()`  

```csharp
public TutorialZoningTriggerPrefab();
```


## Methods

- `protected virtual GenerateBlinkTags() : System.Void`  

```csharp
protected virtual System.Void GenerateBlinkTags();
```

- `public virtual GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs) : System.Void`  

```csharp
public virtual System.Void GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs);
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


