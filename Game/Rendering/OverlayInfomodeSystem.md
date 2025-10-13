# Game.Rendering.OverlayInfomodeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class OverlayInfomodeSystem : Game.GameSystemBase
{
    private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem;
    private Game.Rendering.WaterRenderSystem m_WaterRenderSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.WindSystem m_WindSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Tools.TelecomPreviewSystem m_TelecomCoverageSystem;
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Simulation.LandValueSystem m_LandValueSystem;
    private Game.Simulation.PopulationToGridSystem m_PopulationToGridSystem;
    private Game.Simulation.AvailabilityInfoToGridSystem m_AvailabilityInfoToGridSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Unity.Entities.EntityQuery m_HappinessParameterQuery;
    private UnityEngine.Texture2D m_TerrainTexture;
    private UnityEngine.Texture2D m_WaterTexture;
    private UnityEngine.Texture2D m_WindTexture;
    private Unity.Jobs.JobHandle m_Dependency;
    private Game.Rendering.OverlayInfomodeSystem+TypeHandle __TypeHandle;

    public OverlayInfomodeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void ApplyOverlay();
    private Unity.Collections.NativeArray<System.Byte> GetTerrainTextureData<T>(Game.Simulation.CellMapData<T> cellMapData);
    private Unity.Collections.NativeArray<System.Byte> GetTerrainTextureData(Unity.Mathematics.int2 size);
    private Unity.Collections.NativeArray<System.Byte> GetWaterTextureData<T>(Game.Simulation.CellMapData<T> cellMapData);
    private Unity.Collections.NativeArray<System.Byte> GetWaterTextureData(Unity.Mathematics.int2 size);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem`  

```csharp
private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem;
```

- `private Game.Rendering.WaterRenderSystem m_WaterRenderSystem`  

```csharp
private Game.Rendering.WaterRenderSystem m_WaterRenderSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.WindSystem m_WindSystem`  

```csharp
private Game.Simulation.WindSystem m_WindSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Tools.TelecomPreviewSystem m_TelecomCoverageSystem`  

```csharp
private Game.Tools.TelecomPreviewSystem m_TelecomCoverageSystem;
```

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Simulation.LandValueSystem m_LandValueSystem`  

```csharp
private Game.Simulation.LandValueSystem m_LandValueSystem;
```

- `private Game.Simulation.PopulationToGridSystem m_PopulationToGridSystem`  

```csharp
private Game.Simulation.PopulationToGridSystem m_PopulationToGridSystem;
```

- `private Game.Simulation.AvailabilityInfoToGridSystem m_AvailabilityInfoToGridSystem`  

```csharp
private Game.Simulation.AvailabilityInfoToGridSystem m_AvailabilityInfoToGridSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HappinessParameterQuery;
```

- `private UnityEngine.Texture2D m_TerrainTexture`  

```csharp
private UnityEngine.Texture2D m_TerrainTexture;
```

- `private UnityEngine.Texture2D m_WaterTexture`  

```csharp
private UnityEngine.Texture2D m_WaterTexture;
```

- `private UnityEngine.Texture2D m_WindTexture`  

```csharp
private UnityEngine.Texture2D m_WindTexture;
```

- `private Unity.Jobs.JobHandle m_Dependency`  

```csharp
private Unity.Jobs.JobHandle m_Dependency;
```

- `private Game.Rendering.OverlayInfomodeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.OverlayInfomodeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public OverlayInfomodeSystem()`  

```csharp
public OverlayInfomodeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public ApplyOverlay() : System.Void`  

```csharp
public System.Void ApplyOverlay();
```

- `private GetTerrainTextureData<T>(Game.Simulation.CellMapData<T> cellMapData) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
private Unity.Collections.NativeArray<System.Byte> GetTerrainTextureData<T>(Game.Simulation.CellMapData<T> cellMapData);
```

- `private GetTerrainTextureData(Unity.Mathematics.int2 size) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
private Unity.Collections.NativeArray<System.Byte> GetTerrainTextureData(Unity.Mathematics.int2 size);
```

- `private GetWaterTextureData<T>(Game.Simulation.CellMapData<T> cellMapData) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
private Unity.Collections.NativeArray<System.Byte> GetWaterTextureData<T>(Game.Simulation.CellMapData<T> cellMapData);
```

- `private GetWaterTextureData(Unity.Mathematics.int2 size) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
private Unity.Collections.NativeArray<System.Byte> GetWaterTextureData(Unity.Mathematics.int2 size);
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Rendering.OverlayInfomodeSystem+ClearJob`  
- `Game.Rendering.OverlayInfomodeSystem+GroundWaterJob`  
- `Game.Rendering.OverlayInfomodeSystem+GroundPollutionJob`  
- `Game.Rendering.OverlayInfomodeSystem+NoisePollutionJob`  
- `Game.Rendering.OverlayInfomodeSystem+AirPollutionJob`  
- `Game.Rendering.OverlayInfomodeSystem+WindJob`  
- `Game.Rendering.OverlayInfomodeSystem+TelecomCoverageJob`  
- `Game.Rendering.OverlayInfomodeSystem+FertilityJob`  
- `Game.Rendering.OverlayInfomodeSystem+OreJob`  
- `Game.Rendering.OverlayInfomodeSystem+OilJob`  
- `Game.Rendering.OverlayInfomodeSystem+FishJob`  
- `Game.Rendering.OverlayInfomodeSystem+LandValueJob`  
- `Game.Rendering.OverlayInfomodeSystem+PopulationJob`  
- `Game.Rendering.OverlayInfomodeSystem+AttractionJob`  
- `Game.Rendering.OverlayInfomodeSystem+CustomerJob`  
- `Game.Rendering.OverlayInfomodeSystem+WorkplaceJob`  
- `Game.Rendering.OverlayInfomodeSystem+ServiceJob`  
- `Game.Rendering.OverlayInfomodeSystem+GroundWaterPollutionJob`  
- `Game.Rendering.OverlayInfomodeSystem+TypeHandle`  

