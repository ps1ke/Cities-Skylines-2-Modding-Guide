# Game.Buildings.WaterPoweredInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPoweredInitializeSystem : Game.GameSystemBase
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_WaterPoweredQuery;
    private Game.Buildings.WaterPoweredInitializeSystem+TypeHandle __TypeHandle;

    public WaterPoweredInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_WaterPoweredQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaterPoweredQuery;
```

- `private Game.Buildings.WaterPoweredInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.WaterPoweredInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPoweredInitializeSystem()`  

```csharp
public WaterPoweredInitializeSystem();
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

- `Game.Buildings.WaterPoweredInitializeSystem+WaterPoweredInitializeJob`  
- `Game.Buildings.WaterPoweredInitializeSystem+TypeHandle`  

