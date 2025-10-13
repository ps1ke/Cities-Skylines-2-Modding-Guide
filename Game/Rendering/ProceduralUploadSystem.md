# Game.Rendering.ProceduralUploadSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ProceduralUploadSystem : Game.GameSystemBase
{
    private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem;
    private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.RenderPrefabBase m_OverridePrefab;
    private Colossal.Collections.NativeAccumulator<Game.Rendering.ProceduralUploadSystem+UploadData> m_UploadData;
    private Unity.Jobs.JobHandle m_PrepareDeps;
    private Unity.Entities.Entity m_OverrideEntity;
    private Game.Rendering.LightState m_OverrideLightState;
    private System.Int32 m_OverrideSingleLightIndex;
    private System.Int32 m_OverrideMultiLightIndex;
    private System.Single m_OverrideTime;
    private Game.Rendering.ProceduralUploadSystem+TypeHandle __TypeHandle;

    public ProceduralUploadSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void SetOverride(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase prefab, System.Int32 singleLightIndex, System.Int32 multiLightIndex);
    private System.Void UpdateOverride(Game.Rendering.ProceduralUploadSystem+UploadData& emissiveData);
}
```


## Fields

- `private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem`  

```csharp
private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem;
```

- `private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem`  

```csharp
private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.RenderPrefabBase m_OverridePrefab`  

```csharp
private Game.Prefabs.RenderPrefabBase m_OverridePrefab;
```

- `private Colossal.Collections.NativeAccumulator<Game.Rendering.ProceduralUploadSystem+UploadData> m_UploadData`  

```csharp
private Colossal.Collections.NativeAccumulator<Game.Rendering.ProceduralUploadSystem+UploadData> m_UploadData;
```

- `private Unity.Jobs.JobHandle m_PrepareDeps`  

```csharp
private Unity.Jobs.JobHandle m_PrepareDeps;
```

- `private Unity.Entities.Entity m_OverrideEntity`  

```csharp
private Unity.Entities.Entity m_OverrideEntity;
```

- `private Game.Rendering.LightState m_OverrideLightState`  

```csharp
private Game.Rendering.LightState m_OverrideLightState;
```

- `private System.Int32 m_OverrideSingleLightIndex`  

```csharp
private System.Int32 m_OverrideSingleLightIndex;
```

- `private System.Int32 m_OverrideMultiLightIndex`  

```csharp
private System.Int32 m_OverrideMultiLightIndex;
```

- `private System.Single m_OverrideTime`  

```csharp
private System.Single m_OverrideTime;
```

- `private Game.Rendering.ProceduralUploadSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.ProceduralUploadSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ProceduralUploadSystem()`  

```csharp
public ProceduralUploadSystem();
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

- `public SetOverride(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase prefab, System.Int32 singleLightIndex, System.Int32 multiLightIndex) : System.Void`  

```csharp
public System.Void SetOverride(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase prefab, System.Int32 singleLightIndex, System.Int32 multiLightIndex);
```

- `private UpdateOverride(Game.Rendering.ProceduralUploadSystem+UploadData& emissiveData) : System.Void`  

```csharp
private System.Void UpdateOverride(Game.Rendering.ProceduralUploadSystem+UploadData& emissiveData);
```


## Nested types

- `Game.Rendering.ProceduralUploadSystem+Prepare`  
- `Game.Rendering.ProceduralUploadSystem+UploadData`  
- `Game.Rendering.ProceduralUploadSystem+ProceduralPrepareJob`  
- `Game.Rendering.ProceduralUploadSystem+ProceduralUploadJob`  
- `Game.Rendering.ProceduralUploadSystem+TypeHandle`  

