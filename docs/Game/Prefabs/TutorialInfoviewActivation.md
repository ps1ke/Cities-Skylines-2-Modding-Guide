# Game.Prefabs.TutorialInfoviewActivation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TutorialActivation`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TutorialInfoviewActivation : Game.Prefabs.TutorialActivation, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.InfoviewPrefab m_Infoview;

    public TutorialInfoviewActivation();

    public virtual System.Void GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.InfoviewPrefab m_Infoview`  

```csharp
public Game.Prefabs.InfoviewPrefab m_Infoview;
```


## Constructors

- `public TutorialInfoviewActivation()`  

```csharp
public TutorialInfoviewActivation();
```


## Methods

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


