# Game.Prefabs.TutorialActivation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

## Code

```csharp
public abstract class TutorialActivation : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Boolean ignoreUnlockDependencies { get; }

    protected TutorialActivation();

    public virtual System.Void GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs);
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

```csharp
public System.Boolean ignoreUnlockDependencies { get; }
```


## Constructors

- `protected TutorialActivation()`  

```csharp
protected TutorialActivation();
```


## Methods

- `public virtual GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs) : System.Void`  

```csharp
public virtual System.Void GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs);
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


