# Game.Simulation.WaterPipeGraphDeleteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipeGraphDeleteSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DeletedConnectionQuery;
    private Unity.Entities.EntityQuery m_DeletedValveNodeQuery;
    private Game.Simulation.WaterPipeGraphDeleteSystem+TypeHandle __TypeHandle;

    public WaterPipeGraphDeleteSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier1 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DeletedConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedConnectionQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedValveNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedValveNodeQuery;
```

- `private Game.Simulation.WaterPipeGraphDeleteSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPipeGraphDeleteSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPipeGraphDeleteSystem()`  

```csharp
public WaterPipeGraphDeleteSystem();
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

- `Game.Simulation.WaterPipeGraphDeleteSystem+DeleteConnectionsJob`  
- `Game.Simulation.WaterPipeGraphDeleteSystem+DeleteValveNodesJob`  
- `Game.Simulation.WaterPipeGraphDeleteSystem+TypeHandle`  

