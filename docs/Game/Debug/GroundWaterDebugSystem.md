# Game.Debug.GroundWaterDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class GroundWaterDebugSystem : Game.GameSystemBase
{
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;

    public GroundWaterDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```


## Constructors

- `public GroundWaterDebugSystem()`  

```csharp
public GroundWaterDebugSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Debug.GroundWaterDebugSystem+GroundWaterGizmoJob`  

