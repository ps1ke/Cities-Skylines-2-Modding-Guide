# Game.Debug.WaterCullingDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

## Code

```csharp
public class WaterCullingDebugSystem : Game.Debug.BaseDebugSystem
{
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Debug.BaseDebugSystem+Option m_ActiveWaterCellOption;
    private Game.Debug.BaseDebugSystem+Option m_FixedHeight;

    public WaterCullingDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_ActiveWaterCellOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ActiveWaterCellOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_FixedHeight`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_FixedHeight;
```


## Constructors

- `public WaterCullingDebugSystem()`  

```csharp
public WaterCullingDebugSystem();
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


