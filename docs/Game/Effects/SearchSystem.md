# Game.Effects.SearchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SearchSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Effects.EffectFlagSystem m_EffectFlagSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Effects.EffectControlData m_EffectControlData;
    private Colossal.Collections.NativeQuadTree<Game.Effects.SourceInfo, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
    private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Effects.SearchSystem+AddedSource> m_AddedSources;
    private Unity.Entities.EntityQuery m_UpdatedEffectsQuery;
    private Unity.Entities.EntityQuery m_AllEffectsQuery;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private System.Boolean m_Loaded;
    private Game.Effects.SearchSystem+TypeHandle __TypeHandle;

    public SearchSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
    public static Game.Common.QuadTreeBoundsXZ GetBounds(Unity.Collections.NativeArray<Game.Objects.Transform> transforms, Unity.Collections.NativeArray<Game.Net.Curve> curves, System.Int32 index, Game.Prefabs.Effect effect, Unity.Entities.ComponentLookup`1[[Game.Prefabs.LightEffectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabLightEffectData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.AudioEffectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabAudioEffectData);
    private System.Boolean GetLoaded();
    public Colossal.Collections.NativeQuadTree<Game.Effects.SourceInfo, Game.Common.QuadTreeBoundsXZ> GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Effects.EffectFlagSystem m_EffectFlagSystem`  

```csharp
private Game.Effects.EffectFlagSystem m_EffectFlagSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Effects.EffectControlData m_EffectControlData`  

```csharp
private Game.Effects.EffectControlData m_EffectControlData;
```

- `private Colossal.Collections.NativeQuadTree<Game.Effects.SourceInfo, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  

```csharp
private Colossal.Collections.NativeQuadTree<Game.Effects.SourceInfo, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
```

- `private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Effects.SearchSystem+AddedSource> m_AddedSources`  

```csharp
private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Effects.SearchSystem+AddedSource> m_AddedSources;
```

- `private Unity.Entities.EntityQuery m_UpdatedEffectsQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedEffectsQuery;
```

- `private Unity.Entities.EntityQuery m_AllEffectsQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllEffectsQuery;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Effects.SearchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Effects.SearchSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SearchSystem()`  

```csharp
public SearchSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddSearchTreeReader(Unity.Jobs.JobHandle jobHandle);
```

- `public AddSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddSearchTreeWriter(Unity.Jobs.JobHandle jobHandle);
```

- `public static GetBounds(Unity.Collections.NativeArray<Game.Objects.Transform> transforms, Unity.Collections.NativeArray<Game.Net.Curve> curves, System.Int32 index, Game.Prefabs.Effect effect, Unity.Entities.ComponentLookup`1[[Game.Prefabs.LightEffectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabLightEffectData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.AudioEffectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabAudioEffectData) : Game.Common.QuadTreeBoundsXZ`  

```csharp
public static Game.Common.QuadTreeBoundsXZ GetBounds(Unity.Collections.NativeArray<Game.Objects.Transform> transforms, Unity.Collections.NativeArray<Game.Net.Curve> curves, System.Int32 index, Game.Prefabs.Effect effect, Unity.Entities.ComponentLookup`1[[Game.Prefabs.LightEffectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabLightEffectData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.AudioEffectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabAudioEffectData);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `public GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Game.Effects.SourceInfo, Game.Common.QuadTreeBoundsXZ>`  

```csharp
public Colossal.Collections.NativeQuadTree<Game.Effects.SourceInfo, Game.Common.QuadTreeBoundsXZ> GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
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

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Effects.SearchSystem+AddedSource`  
- `Game.Effects.SearchSystem+UpdateSearchTreeJob`  
- `Game.Effects.SearchSystem+TypeHandle`  

