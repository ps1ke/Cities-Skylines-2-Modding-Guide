# Game.Effects.EffectControlSystem

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EffectControlSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.Effects.VFXSystem m_VFXSystem;
    private Game.Effects.SearchSystem m_SearchSystem;
    private Game.Effects.EffectFlagSystem m_EffectFlagSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.BatchDataSystem m_BatchDataSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Effects.EffectControlData m_EffectControlData;
    private Unity.Collections.NativeList<Game.Effects.EnabledEffectData> m_EnabledData;
    private Unity.Entities.EntityQuery m_UpdatedEffectsQuery;
    private Unity.Entities.EntityQuery m_AllEffectsQuery;
    private Unity.Jobs.JobHandle m_EnabledWriteDependencies;
    private Unity.Jobs.JobHandle m_EnabledReadDependencies;
    private Unity.Mathematics.float3 m_PrevCameraPosition;
    private Unity.Mathematics.float3 m_PrevCameraDirection;
    private Unity.Mathematics.float4 m_PrevLodParameters;
    private System.Boolean m_Loaded;
    private System.Boolean m_ResetPrevious;
    private Game.Effects.EffectControlSystem+TypeHandle __TypeHandle;

    public EffectControlSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddEnabledDataReader(Unity.Jobs.JobHandle dependencies);
    public System.Void AddEnabledDataWriter(Unity.Jobs.JobHandle dependencies);
    public Unity.Collections.NativeList<Game.Effects.EnabledEffectData> GetEnabledData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    private System.Boolean GetLoaded();
    public System.Void GetLodParameters(Unity.Mathematics.float4& lodParameters, Unity.Mathematics.float3& cameraPosition, Unity.Mathematics.float3& cameraDirection);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Effects.VFXSystem m_VFXSystem`  

```csharp
private Game.Effects.VFXSystem m_VFXSystem;
```

- `private Game.Effects.SearchSystem m_SearchSystem`  

```csharp
private Game.Effects.SearchSystem m_SearchSystem;
```

- `private Game.Effects.EffectFlagSystem m_EffectFlagSystem`  

```csharp
private Game.Effects.EffectFlagSystem m_EffectFlagSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.BatchDataSystem m_BatchDataSystem`  

```csharp
private Game.Rendering.BatchDataSystem m_BatchDataSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Effects.EffectControlData m_EffectControlData`  

```csharp
private Game.Effects.EffectControlData m_EffectControlData;
```

- `private Unity.Collections.NativeList<Game.Effects.EnabledEffectData> m_EnabledData`  

```csharp
private Unity.Collections.NativeList<Game.Effects.EnabledEffectData> m_EnabledData;
```

- `private Unity.Entities.EntityQuery m_UpdatedEffectsQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedEffectsQuery;
```

- `private Unity.Entities.EntityQuery m_AllEffectsQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllEffectsQuery;
```

- `private Unity.Jobs.JobHandle m_EnabledWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_EnabledWriteDependencies;
```

- `private Unity.Jobs.JobHandle m_EnabledReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_EnabledReadDependencies;
```

- `private Unity.Mathematics.float3 m_PrevCameraPosition`  

```csharp
private Unity.Mathematics.float3 m_PrevCameraPosition;
```

- `private Unity.Mathematics.float3 m_PrevCameraDirection`  

```csharp
private Unity.Mathematics.float3 m_PrevCameraDirection;
```

- `private Unity.Mathematics.float4 m_PrevLodParameters`  

```csharp
private Unity.Mathematics.float4 m_PrevLodParameters;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private System.Boolean m_ResetPrevious`  

```csharp
private System.Boolean m_ResetPrevious;
```

- `private Game.Effects.EffectControlSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Effects.EffectControlSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EffectControlSystem()`  

```csharp
public EffectControlSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddEnabledDataReader(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void AddEnabledDataReader(Unity.Jobs.JobHandle dependencies);
```

- `public AddEnabledDataWriter(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void AddEnabledDataWriter(Unity.Jobs.JobHandle dependencies);
```

- `public GetEnabledData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Effects.EnabledEffectData>`  

```csharp
public Unity.Collections.NativeList<Game.Effects.EnabledEffectData> GetEnabledData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `public GetLodParameters(Unity.Mathematics.float4& lodParameters, Unity.Mathematics.float3& cameraPosition, Unity.Mathematics.float3& cameraDirection) : System.Void`  

```csharp
public System.Void GetLodParameters(Unity.Mathematics.float4& lodParameters, Unity.Mathematics.float3& cameraPosition, Unity.Mathematics.float3& cameraDirection);
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

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Effects.EffectControlSystem+EffectControlJob`  
- `Game.Effects.EffectControlSystem+EffectCullingJob`  
- `Game.Effects.EffectControlSystem+TreeCullingJob1`  
- `Game.Effects.EffectControlSystem+TreeCullingJob2`  
- `Game.Effects.EffectControlSystem+TreeCullingIterator`  
- `Game.Effects.EffectControlSystem+ActionFlags`  
- `Game.Effects.EffectControlSystem+EnabledAction`  
- `Game.Effects.EffectControlSystem+OverflowAction`  
- `Game.Effects.EffectControlSystem+EnabledActionJob`  
- `Game.Effects.EffectControlSystem+ResizeEnabledDataJob`  
- `Game.Effects.EffectControlSystem+TypeHandle`  

