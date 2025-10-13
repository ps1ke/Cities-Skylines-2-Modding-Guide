# Game.Events.ImpactSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ImpactSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_ImpactQuery;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingPersonalCarAddTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingTaxiAddTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingServiceCarAddTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrailerAddTypes;
    private Game.Events.ImpactSystem+TypeHandle __TypeHandle;

    public ImpactSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_ImpactQuery`  

```csharp
private Unity.Entities.EntityQuery m_ImpactQuery;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarRemoveTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingPersonalCarAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingPersonalCarAddTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingTaxiAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingTaxiAddTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingServiceCarAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingServiceCarAddTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrailerAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrailerAddTypes;
```

- `private Game.Events.ImpactSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.ImpactSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ImpactSystem()`  

```csharp
public ImpactSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Events.ImpactSystem+AddImpactJob`  
- `Game.Events.ImpactSystem+TypeHandle`  

