# Game.Prefabs.TutorialHealthProblemActivation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TutorialActivation`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TutorialHealthProblemActivation : Game.Prefabs.TutorialActivation, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Citizens.HealthProblemFlags m_Flags;
    public System.Int32 m_RequiredCount;

    public TutorialHealthProblemActivation();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Citizens.HealthProblemFlags m_Flags`  

```csharp
public Game.Citizens.HealthProblemFlags m_Flags;
```

- `public System.Int32 m_RequiredCount`  

```csharp
public System.Int32 m_RequiredCount;
```


## Constructors

- `public TutorialHealthProblemActivation()`  

```csharp
public TutorialHealthProblemActivation();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


