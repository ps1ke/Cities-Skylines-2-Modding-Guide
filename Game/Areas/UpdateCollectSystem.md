# Game.Areas.UpdateCollectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpdateCollectSystem : Game.GameSystemBase
{
    private Game.Areas.SearchSystem m_SearchSystem;
    private Game.Areas.UpdateCollectSystem+UpdateBufferData m_LotData;
    private Game.Areas.UpdateCollectSystem+UpdateBufferData m_DistrictData;
    private Game.Areas.UpdateCollectSystem+UpdateBufferData m_MapTileData;
    private Game.Areas.UpdateCollectSystem+UpdateBufferData m_SpaceData;
    private Game.Areas.UpdateCollectSystem+TypeHandle __TypeHandle;

    public System.Boolean lotsUpdated { get; }
    public System.Boolean districtsUpdated { get; }
    public System.Boolean mapTilesUpdated { get; }
    public System.Boolean spacesUpdated { get; }

    public UpdateCollectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddDistrictBoundsReader(Unity.Jobs.JobHandle handle);
    public System.Void AddLotBoundsReader(Unity.Jobs.JobHandle handle);
    public System.Void AddMapTileBoundsReader(Unity.Jobs.JobHandle handle);
    public System.Void AddSpaceBoundsReader(Unity.Jobs.JobHandle handle);
    private Unity.Entities.EntityQuery GetQuery<T>();
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedDistrictBounds(Unity.Jobs.JobHandle& dependencies);
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedLotBounds(Unity.Jobs.JobHandle& dependencies);
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedMapTileBounds(Unity.Jobs.JobHandle& dependencies);
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedSpaceBounds(Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
    private Unity.Jobs.JobHandle UpdateBounds(Game.Areas.UpdateCollectSystem+UpdateBufferData& data, Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Areas.SearchSystem m_SearchSystem`  

```csharp
private Game.Areas.SearchSystem m_SearchSystem;
```

- `private Game.Areas.UpdateCollectSystem+UpdateBufferData m_LotData`  

```csharp
private Game.Areas.UpdateCollectSystem+UpdateBufferData m_LotData;
```

- `private Game.Areas.UpdateCollectSystem+UpdateBufferData m_DistrictData`  

```csharp
private Game.Areas.UpdateCollectSystem+UpdateBufferData m_DistrictData;
```

- `private Game.Areas.UpdateCollectSystem+UpdateBufferData m_MapTileData`  

```csharp
private Game.Areas.UpdateCollectSystem+UpdateBufferData m_MapTileData;
```

- `private Game.Areas.UpdateCollectSystem+UpdateBufferData m_SpaceData`  

```csharp
private Game.Areas.UpdateCollectSystem+UpdateBufferData m_SpaceData;
```

- `private Game.Areas.UpdateCollectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.UpdateCollectSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean lotsUpdated { get }`  

```csharp
public System.Boolean lotsUpdated { get; }
```

- `public System.Boolean districtsUpdated { get }`  

```csharp
public System.Boolean districtsUpdated { get; }
```

- `public System.Boolean mapTilesUpdated { get }`  

```csharp
public System.Boolean mapTilesUpdated { get; }
```

- `public System.Boolean spacesUpdated { get }`  

```csharp
public System.Boolean spacesUpdated { get; }
```


## Constructors

- `public UpdateCollectSystem()`  

```csharp
public UpdateCollectSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddDistrictBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddDistrictBoundsReader(Unity.Jobs.JobHandle handle);
```

- `public AddLotBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddLotBoundsReader(Unity.Jobs.JobHandle handle);
```

- `public AddMapTileBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddMapTileBoundsReader(Unity.Jobs.JobHandle handle);
```

- `public AddSpaceBoundsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddSpaceBoundsReader(Unity.Jobs.JobHandle handle);
```

- `private GetQuery<T>() : Unity.Entities.EntityQuery`  

```csharp
private Unity.Entities.EntityQuery GetQuery<T>();
```

- `public GetUpdatedDistrictBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedDistrictBounds(Unity.Jobs.JobHandle& dependencies);
```

- `public GetUpdatedLotBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedLotBounds(Unity.Jobs.JobHandle& dependencies);
```

- `public GetUpdatedMapTileBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedMapTileBounds(Unity.Jobs.JobHandle& dependencies);
```

- `public GetUpdatedSpaceBounds(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdatedSpaceBounds(Unity.Jobs.JobHandle& dependencies);
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

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private UpdateBounds(Game.Areas.UpdateCollectSystem+UpdateBufferData& data, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle UpdateBounds(Game.Areas.UpdateCollectSystem+UpdateBufferData& data, Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Areas.UpdateCollectSystem+UpdateBufferData`  
- `Game.Areas.UpdateCollectSystem+CollectUpdatedAreaBoundsJob`  
- `Game.Areas.UpdateCollectSystem+DequeueBoundsJob`  
- `Game.Areas.UpdateCollectSystem+TypeHandle`  

