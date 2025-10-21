# Game.Buildings.ParkInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ParkInitializeSystem : Game.GameSystemBase
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_ParkQuery;
    private Game.Buildings.ParkInitializeSystem+TypeHandle __TypeHandle;

    public ParkInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_ParkQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkQuery;
```

- `private Game.Buildings.ParkInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.ParkInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ParkInitializeSystem()`  

```csharp
public ParkInitializeSystem();
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

- `Game.Buildings.ParkInitializeSystem+InitializeParksJob`  
- `Game.Buildings.ParkInitializeSystem+TypeHandle`  

