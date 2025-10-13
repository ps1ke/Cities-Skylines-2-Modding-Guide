# Game.Net.OverrideSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class OverrideSystem : Game.GameSystemBase
{
    private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Net.OverrideSystem+TypeHandle __TypeHandle;
    private static const System.Single MIN_PARALLEL_FENCE_DISTANCE;

    public OverrideSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle CollectUpdatedLanes(Unity.Collections.NativeList<Unity.Entities.Entity> updateLanesList);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem`  

```csharp
private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Net.OverrideSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.OverrideSystem+TypeHandle __TypeHandle;
```

- `private static const System.Single MIN_PARALLEL_FENCE_DISTANCE`  

```csharp
private static const System.Single MIN_PARALLEL_FENCE_DISTANCE;
```


## Constructors

- `public OverrideSystem()`  

```csharp
public OverrideSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private CollectUpdatedLanes(Unity.Collections.NativeList<Unity.Entities.Entity> updateLanesList) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle CollectUpdatedLanes(Unity.Collections.NativeList<Unity.Entities.Entity> updateLanesList);
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


## Nested types

- `Game.Net.OverrideSystem+TreeAction`  
- `Game.Net.OverrideSystem+UpdateOverriddenLayersJob`  
- `Game.Net.OverrideSystem+FindUpdatedLanesJob`  
- `Game.Net.OverrideSystem+CollectObjectsJob`  
- `Game.Net.OverrideSystem+CheckLaneOverrideJob`  
- `Game.Net.OverrideSystem+TypeHandle`  

