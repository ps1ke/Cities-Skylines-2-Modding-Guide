# Game.Effects.VFXSystem

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class VFXSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private System.Collections.Generic.Queue<Unity.Collections.NativeQueue<Game.Effects.VFXUpdateInfo>> m_SourceUpdateQueue;
    private Unity.Jobs.JobHandle m_SourceUpdateWriter;
    private Unity.Entities.EntityQuery m_VFXPrefabQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private System.Boolean m_Initialized;
    private Game.Effects.VFXSystem+EffectInfo[] m_Effects;
    private Unity.Jobs.JobHandle m_TextureUpdate;
    private Game.Rendering.WindTextureSystem m_WindTextureSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Effects.EffectControlSystem m_EffectControlSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;

    public VFXSystem();

    public System.Void AddSourceUpdateWriter(Unity.Jobs.JobHandle jobHandle);
    private System.Void ClearQueue();
    public Unity.Collections.NativeQueue<Game.Effects.VFXUpdateInfo> GetSourceUpdateData();
    private System.Boolean Initialize();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private System.Collections.Generic.Queue<Unity.Collections.NativeQueue<Game.Effects.VFXUpdateInfo>> m_SourceUpdateQueue`  

```csharp
private System.Collections.Generic.Queue<Unity.Collections.NativeQueue<Game.Effects.VFXUpdateInfo>> m_SourceUpdateQueue;
```

- `private Unity.Jobs.JobHandle m_SourceUpdateWriter`  

```csharp
private Unity.Jobs.JobHandle m_SourceUpdateWriter;
```

- `private Unity.Entities.EntityQuery m_VFXPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_VFXPrefabQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private System.Boolean m_Initialized`  

```csharp
private System.Boolean m_Initialized;
```

- `private Game.Effects.VFXSystem+EffectInfo[] m_Effects`  

```csharp
private Game.Effects.VFXSystem+EffectInfo[] m_Effects;
```

- `private Unity.Jobs.JobHandle m_TextureUpdate`  

```csharp
private Unity.Jobs.JobHandle m_TextureUpdate;
```

- `private Game.Rendering.WindTextureSystem m_WindTextureSystem`  

```csharp
private Game.Rendering.WindTextureSystem m_WindTextureSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Effects.EffectControlSystem m_EffectControlSystem`  

```csharp
private Game.Effects.EffectControlSystem m_EffectControlSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```


## Constructors

- `public VFXSystem()`  

```csharp
public VFXSystem();
```


## Methods

- `public AddSourceUpdateWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddSourceUpdateWriter(Unity.Jobs.JobHandle jobHandle);
```

- `private ClearQueue() : System.Void`  

```csharp
private System.Void ClearQueue();
```

- `public GetSourceUpdateData() : Unity.Collections.NativeQueue<Game.Effects.VFXUpdateInfo>`  

```csharp
public Unity.Collections.NativeQueue<Game.Effects.VFXUpdateInfo> GetSourceUpdateData();
```

- `private Initialize() : System.Boolean`  

```csharp
private System.Boolean Initialize();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Effects.VFXSystem+VFXIDs`  
- `Game.Effects.VFXSystem+EffectInfo`  
- `Game.Effects.VFXSystem+VFXTextureUpdateJob`  

