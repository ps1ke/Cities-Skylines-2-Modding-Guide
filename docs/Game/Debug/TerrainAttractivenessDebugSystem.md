# Game.Debug.TerrainAttractivenessDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TerrainAttractivenessDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_ParameterQuery;
    private Colossal.GizmosSystem m_GizmosSystem;

    public TerrainAttractivenessDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem`  

```csharp
private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_ParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParameterQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```


## Constructors

- `public TerrainAttractivenessDebugSystem()`  

```csharp
public TerrainAttractivenessDebugSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Debug.TerrainAttractivenessDebugSystem+TerrainAttractivenessGizmoJob`  

