# Game.Simulation.ElectricityBuildingGraphSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ElectricityBuildingGraphSystem : Game.GameSystemBase
{
    private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem;
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Game.Common.ModificationBarrier4B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_UpdatedBuildingQuery;
    private Game.Simulation.ElectricityBuildingGraphSystem+TypeHandle __TypeHandle;

    public ElectricityBuildingGraphSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    internal static Unity.Entities.EntityQueryDesc <OnCreate>g__CreatedUpdatedBuildingDesc|4_0(Unity.Entities.ComponentType[] all);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem`  

```csharp
private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem;
```

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_UpdatedBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedBuildingQuery;
```

- `private Game.Simulation.ElectricityBuildingGraphSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ElectricityBuildingGraphSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ElectricityBuildingGraphSystem()`  

```csharp
public ElectricityBuildingGraphSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `internal static <OnCreate>g__CreatedUpdatedBuildingDesc|4_0(Unity.Entities.ComponentType[] all) : Unity.Entities.EntityQueryDesc`  

```csharp
internal static Unity.Entities.EntityQueryDesc <OnCreate>g__CreatedUpdatedBuildingDesc|4_0(Unity.Entities.ComponentType[] all);
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

- `Game.Simulation.ElectricityBuildingGraphSystem+UpdateBuildingConnectionsJob`  
- `Game.Simulation.ElectricityBuildingGraphSystem+TypeHandle`  

