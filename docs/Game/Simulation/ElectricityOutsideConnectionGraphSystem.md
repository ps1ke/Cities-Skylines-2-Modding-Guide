# Game.Simulation.ElectricityOutsideConnectionGraphSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ElectricityOutsideConnectionGraphSystem : Game.GameSystemBase
{
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Game.Common.ModificationBarrier3 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CreatedConnectionQuery;
    private Game.Simulation.ElectricityOutsideConnectionGraphSystem+TypeHandle __TypeHandle;

    public ElectricityOutsideConnectionGraphSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Game.Common.ModificationBarrier3 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier3 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_CreatedConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedConnectionQuery;
```

- `private Game.Simulation.ElectricityOutsideConnectionGraphSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ElectricityOutsideConnectionGraphSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ElectricityOutsideConnectionGraphSystem()`  

```csharp
public ElectricityOutsideConnectionGraphSystem();
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

- `Game.Simulation.ElectricityOutsideConnectionGraphSystem+CreateOutsideConnectionsJob`  
- `Game.Simulation.ElectricityOutsideConnectionGraphSystem+TypeHandle`  

