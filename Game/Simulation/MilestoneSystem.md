# Game.Simulation.MilestoneSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IMilestoneSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MilestoneSystem : Game.GameSystemBase, Game.Simulation.IMilestoneSystem
{
    private System.Int32 m_LastRequired;
    private System.Int32 m_NextRequired;
    private System.Int32 m_Progress;
    private System.Int32 m_NextMilestone;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Unity.Entities.EntityArchetype m_MilestoneReachedEventArchetype;
    private Unity.Entities.EntityQuery m_MilestoneLevelGroup;
    private Unity.Entities.EntityQuery m_XPGroup;
    private Unity.Entities.EntityQuery m_MilestoneGroup;

    public System.Int32 currentXP { get; }
    public System.Int32 requiredXP { get; }
    public System.Int32 lastRequiredXP { get; }
    public System.Int32 nextRequiredXP { get; }
    public System.Single progress { get; }
    public System.Int32 nextMilestone { get; }

    public MilestoneSystem();

    private System.Void NextMilestone(System.Int32 index);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    private System.Boolean TryGetMilestone(System.Int32 index, Unity.Entities.Entity& entity, Game.Prefabs.MilestoneData& milestone);
    public System.Void UnlockAllMilestones();
}
```


## Fields

- `private System.Int32 m_LastRequired`  

```csharp
private System.Int32 m_LastRequired;
```

- `private System.Int32 m_NextRequired`  

```csharp
private System.Int32 m_NextRequired;
```

- `private System.Int32 m_Progress`  

```csharp
private System.Int32 m_Progress;
```

- `private System.Int32 m_NextMilestone`  

```csharp
private System.Int32 m_NextMilestone;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Common.ModificationEndBarrier m_ModificationEndBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_MilestoneReachedEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_MilestoneReachedEventArchetype;
```

- `private Unity.Entities.EntityQuery m_MilestoneLevelGroup`  

```csharp
private Unity.Entities.EntityQuery m_MilestoneLevelGroup;
```

- `private Unity.Entities.EntityQuery m_XPGroup`  

```csharp
private Unity.Entities.EntityQuery m_XPGroup;
```

- `private Unity.Entities.EntityQuery m_MilestoneGroup`  

```csharp
private Unity.Entities.EntityQuery m_MilestoneGroup;
```


## Properties

- `public System.Int32 currentXP { get }`  

```csharp
public System.Int32 currentXP { get; }
```

- `public System.Int32 requiredXP { get }`  

```csharp
public System.Int32 requiredXP { get; }
```

- `public System.Int32 lastRequiredXP { get }`  

```csharp
public System.Int32 lastRequiredXP { get; }
```

- `public System.Int32 nextRequiredXP { get }`  

```csharp
public System.Int32 nextRequiredXP { get; }
```

- `public System.Single progress { get }`  

```csharp
public System.Single progress { get; }
```

- `public System.Int32 nextMilestone { get }`  

```csharp
public System.Int32 nextMilestone { get; }
```


## Constructors

- `public MilestoneSystem()`  

```csharp
public MilestoneSystem();
```


## Methods

- `private NextMilestone(System.Int32 index) : System.Void`  

```csharp
private System.Void NextMilestone(System.Int32 index);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private TryGetMilestone(System.Int32 index, Unity.Entities.Entity& entity, Game.Prefabs.MilestoneData& milestone) : System.Boolean`  

```csharp
private System.Boolean TryGetMilestone(System.Int32 index, Unity.Entities.Entity& entity, Game.Prefabs.MilestoneData& milestone);
```

- `public UnlockAllMilestones() : System.Void`  

```csharp
public System.Void UnlockAllMilestones();
```


