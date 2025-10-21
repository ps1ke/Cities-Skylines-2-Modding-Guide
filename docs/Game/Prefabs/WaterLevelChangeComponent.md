# Game.Prefabs.WaterLevelChangeComponent

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WaterLevelChangeComponent : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.WaterLevelTargetType m_TargetType;
    public Game.Prefabs.WaterLevelChangeType m_ChangeType;
    public System.Single m_EscalationDelay;
    public System.Boolean m_Evacuate;
    public System.Boolean m_StayIndoors;
    public System.Single m_DangerLevel;

    public WaterLevelChangeComponent();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.WaterLevelTargetType m_TargetType`  

```csharp
public Game.Prefabs.WaterLevelTargetType m_TargetType;
```

- `public Game.Prefabs.WaterLevelChangeType m_ChangeType`  

```csharp
public Game.Prefabs.WaterLevelChangeType m_ChangeType;
```

- `public System.Single m_EscalationDelay`  

```csharp
public System.Single m_EscalationDelay;
```

- `public System.Boolean m_Evacuate`  

```csharp
public System.Boolean m_Evacuate;
```

- `public System.Boolean m_StayIndoors`  

```csharp
public System.Boolean m_StayIndoors;
```

- `public System.Single m_DangerLevel`  

```csharp
public System.Single m_DangerLevel;
```


## Constructors

- `public WaterLevelChangeComponent()`  

```csharp
public WaterLevelChangeComponent();
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


