# Game.Prefabs.ObjectAchievementComponent

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ObjectAchievementComponent : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.ObjectAchievementComponent+ObjectAchievementSetup[] m_Achievements;

    public ObjectAchievementComponent();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.ObjectAchievementComponent+ObjectAchievementSetup[] m_Achievements`  

```csharp
public Game.Prefabs.ObjectAchievementComponent+ObjectAchievementSetup[] m_Achievements;
```


## Constructors

- `public ObjectAchievementComponent()`  

```csharp
public ObjectAchievementComponent();
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


## Nested types

- `Game.Prefabs.ObjectAchievementComponent+ObjectAchievementSetup`  

