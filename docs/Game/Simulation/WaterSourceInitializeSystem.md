# Game.Simulation.WaterSourceInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterSourceInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_WaterSourceQuery;
    private Game.Simulation.WaterSourceInitializeSystem+TypeHandle __TypeHandle;

    public WaterSourceInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_WaterSourceQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaterSourceQuery;
```

- `private Game.Simulation.WaterSourceInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterSourceInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterSourceInitializeSystem()`  

```csharp
public WaterSourceInitializeSystem();
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

- `Game.Simulation.WaterSourceInitializeSystem+InitializeWaterSourcesJob`  
- `Game.Simulation.WaterSourceInitializeSystem+TypeHandle`  

