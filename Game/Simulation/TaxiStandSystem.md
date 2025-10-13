# Game.Simulation.TaxiStandSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TaxiStandSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_StandQuery;
    private Unity.Entities.EntityArchetype m_VehicleRequestArchetype;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.TaxiStandSystem+TypeHandle __TypeHandle;
    public static const System.UInt32 UPDATE_INTERVAL;

    public TaxiStandSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_StandQuery`  

```csharp
private Unity.Entities.EntityQuery m_StandQuery;
```

- `private Unity.Entities.EntityArchetype m_VehicleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_VehicleRequestArchetype;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.TaxiStandSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TaxiStandSystem+TypeHandle __TypeHandle;
```

- `public static const System.UInt32 UPDATE_INTERVAL`  

```csharp
public static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public TaxiStandSystem()`  

```csharp
public TaxiStandSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `Game.Simulation.TaxiStandSystem+TaxiStandTickJob`  
- `Game.Simulation.TaxiStandSystem+TypeHandle`  

