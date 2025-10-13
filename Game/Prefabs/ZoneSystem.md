# Game.Prefabs.ZoneSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ZoneSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_ZonePrefabs;
    private System.Int32 m_ZoneFillColors;
    private System.Int32 m_ZoneEdgeColors;
    private System.Boolean m_IsEditorMode;
    private System.Boolean m_UpdateColors;
    private System.Boolean m_RemovedZones;
    private UnityEngine.Vector4[] m_FillColorArray;
    private UnityEngine.Vector4[] m_EdgeColorArray;
    private Unity.Jobs.JobHandle m_PrefabsReaders;
    private Game.Prefabs.ZoneSystem+TypeHandle __TypeHandle;

    public ZoneSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddPrefabsReader(Unity.Jobs.JobHandle handle);
    private System.Int32 GetNextIndex();
    public Unity.Entities.Entity GetPrefab(Game.Zones.ZoneType zoneType);
    public Game.Prefabs.ZonePrefabs GetPrefabs();
    private System.Void GetZoneColors(UnityEngine.Color color, UnityEngine.Color& occupied, UnityEngine.Color& selected);
    private System.Void InitializeZonePrefabs();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    private System.Void UpdateZoneColors();
    private System.Void UpdateZoneColors(Game.Prefabs.ZonePrefab zonePrefab, Game.Prefabs.ZoneData zoneData);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_ZonePrefabs`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_ZonePrefabs;
```

- `private System.Int32 m_ZoneFillColors`  

```csharp
private System.Int32 m_ZoneFillColors;
```

- `private System.Int32 m_ZoneEdgeColors`  

```csharp
private System.Int32 m_ZoneEdgeColors;
```

- `private System.Boolean m_IsEditorMode`  

```csharp
private System.Boolean m_IsEditorMode;
```

- `private System.Boolean m_UpdateColors`  

```csharp
private System.Boolean m_UpdateColors;
```

- `private System.Boolean m_RemovedZones`  

```csharp
private System.Boolean m_RemovedZones;
```

- `private UnityEngine.Vector4[] m_FillColorArray`  

```csharp
private UnityEngine.Vector4[] m_FillColorArray;
```

- `private UnityEngine.Vector4[] m_EdgeColorArray`  

```csharp
private UnityEngine.Vector4[] m_EdgeColorArray;
```

- `private Unity.Jobs.JobHandle m_PrefabsReaders`  

```csharp
private Unity.Jobs.JobHandle m_PrefabsReaders;
```

- `private Game.Prefabs.ZoneSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.ZoneSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ZoneSystem()`  

```csharp
public ZoneSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddPrefabsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddPrefabsReader(Unity.Jobs.JobHandle handle);
```

- `private GetNextIndex() : System.Int32`  

```csharp
private System.Int32 GetNextIndex();
```

- `public GetPrefab(Game.Zones.ZoneType zoneType) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity GetPrefab(Game.Zones.ZoneType zoneType);
```

- `public GetPrefabs() : Game.Prefabs.ZonePrefabs`  

```csharp
public Game.Prefabs.ZonePrefabs GetPrefabs();
```

- `private GetZoneColors(UnityEngine.Color color, UnityEngine.Color& occupied, UnityEngine.Color& selected) : System.Void`  

```csharp
private System.Void GetZoneColors(UnityEngine.Color color, UnityEngine.Color& occupied, UnityEngine.Color& selected);
```

- `private InitializeZonePrefabs() : System.Void`  

```csharp
private System.Void InitializeZonePrefabs();
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

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private UpdateZoneColors() : System.Void`  

```csharp
private System.Void UpdateZoneColors();
```

- `private UpdateZoneColors(Game.Prefabs.ZonePrefab zonePrefab, Game.Prefabs.ZoneData zoneData) : System.Void`  

```csharp
private System.Void UpdateZoneColors(Game.Prefabs.ZonePrefab zonePrefab, Game.Prefabs.ZoneData zoneData);
```


## Nested types

- `Game.Prefabs.ZoneSystem+TypeHandle`  

