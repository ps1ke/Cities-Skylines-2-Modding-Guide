# Game.Simulation.AttractionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AttractionSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_BuildingGroup;
    private Unity.Entities.EntityQuery m_SettingsQuery;
    private Game.Simulation.AttractionSystem+TypeHandle __TypeHandle;

    public AttractionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public static System.Void SetFactor(Unity.Collections.NativeArray<System.Int32> factors, Game.Simulation.AttractionSystem+AttractivenessFactor factor, System.Single attractiveness);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem`  

```csharp
private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_BuildingGroup`  

```csharp
private Unity.Entities.EntityQuery m_BuildingGroup;
```

- `private Unity.Entities.EntityQuery m_SettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_SettingsQuery;
```

- `private Game.Simulation.AttractionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AttractionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AttractionSystem()`  

```csharp
public AttractionSystem();
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

- `public static SetFactor(Unity.Collections.NativeArray<System.Int32> factors, Game.Simulation.AttractionSystem+AttractivenessFactor factor, System.Single attractiveness) : System.Void`  

```csharp
public static System.Void SetFactor(Unity.Collections.NativeArray<System.Int32> factors, Game.Simulation.AttractionSystem+AttractivenessFactor factor, System.Single attractiveness);
```


## Nested types

- `Game.Simulation.AttractionSystem+AttractivenessFactor`  
- `Game.Simulation.AttractionSystem+AttractivenessJob`  
- `Game.Simulation.AttractionSystem+TypeHandle`  

