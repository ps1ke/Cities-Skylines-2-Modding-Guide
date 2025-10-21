# Game.Tools.TelecomPreviewSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.TelecomCoverage>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TelecomPreviewSystem : Game.Simulation.CellMapSystem<Game.Simulation.TelecomCoverage>
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_DensityQuery;
    private Unity.Entities.EntityQuery m_FacilityQuery;
    private Unity.Entities.EntityQuery m_ModifiedQuery;
    private System.Boolean m_ForceUpdate;
    private Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_Status;
    private Game.Tools.TelecomPreviewSystem+TypeHandle __TypeHandle;

    public Unity.Mathematics.int2 TextureSize { get; }

    public TelecomPreviewSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_DensityQuery`  

```csharp
private Unity.Entities.EntityQuery m_DensityQuery;
```

- `private Unity.Entities.EntityQuery m_FacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_FacilityQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedQuery;
```

- `private System.Boolean m_ForceUpdate`  

```csharp
private System.Boolean m_ForceUpdate;
```

- `private Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_Status`  

```csharp
private Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_Status;
```

- `private Game.Tools.TelecomPreviewSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.TelecomPreviewSystem+TypeHandle __TypeHandle;
```


## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```


## Constructors

- `public TelecomPreviewSystem()`  

```csharp
public TelecomPreviewSystem();
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Tools.TelecomPreviewSystem+TypeHandle`  

