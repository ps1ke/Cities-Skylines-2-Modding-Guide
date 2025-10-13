# Game.Policies.Modify

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct Modify : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Entity;
    public Unity.Entities.Entity m_Policy;
    public Game.Policies.PolicyFlags m_Flags;
    public System.Single m_Adjustment;

    public Modify(Unity.Entities.Entity entity, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment);

}
```


## Fields

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public Unity.Entities.Entity m_Policy`  

```csharp
public Unity.Entities.Entity m_Policy;
```

- `public Game.Policies.PolicyFlags m_Flags`  

```csharp
public Game.Policies.PolicyFlags m_Flags;
```

- `public System.Single m_Adjustment`  

```csharp
public System.Single m_Adjustment;
```


## Constructors

- `public Modify(Unity.Entities.Entity entity, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment)`  

```csharp
public Modify(Entity entity, Entity policy, bool active, float adjustment)
	{
		m_Entity = entity;
		m_Policy = policy;
		m_Flags = (active ? PolicyFlags.Active : ((PolicyFlags)0));
		m_Adjustment = adjustment;
	}
```


