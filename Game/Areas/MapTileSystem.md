# Game.Areas.MapTileSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MapTileSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_MapTileQuery;
    private Unity.Entities.EntityQuery m_DeletedMapTileQuery;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_StartTiles;
    private Game.Areas.MapTileSystem+TypeHandle __TypeHandle;
    private static const System.Int32 LEGACY_GRID_WIDTH;
    private static const System.Int32 LEGACY_GRID_LENGTH;
    private static const System.Single LEGACY_CELL_SIZE;

    public MapTileSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AddOwner(Unity.Mathematics.int2 tile, Unity.Collections.NativeArray<Unity.Entities.Entity> entities);
    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Collections.NativeList<Unity.Entities.Entity> GetStartTiles();
    private System.Void LegacyGenerateMapTiles(System.Boolean editorMode);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Entities.EntityQuery m_MapTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_MapTileQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedMapTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedMapTileQuery;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_StartTiles`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_StartTiles;
```

- `private Game.Areas.MapTileSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.MapTileSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 LEGACY_GRID_WIDTH`  

```csharp
private static const System.Int32 LEGACY_GRID_WIDTH;
```

- `private static const System.Int32 LEGACY_GRID_LENGTH`  

```csharp
private static const System.Int32 LEGACY_GRID_LENGTH;
```

- `private static const System.Single LEGACY_CELL_SIZE`  

```csharp
private static const System.Single LEGACY_CELL_SIZE;
```


## Constructors

- `public MapTileSystem()`  

```csharp
public MapTileSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private AddOwner(Unity.Mathematics.int2 tile, Unity.Collections.NativeArray<Unity.Entities.Entity> entities) : System.Void`  

```csharp
private System.Void AddOwner(Unity.Mathematics.int2 tile, Unity.Collections.NativeArray<Unity.Entities.Entity> entities);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetStartTiles() : Unity.Collections.NativeList<Unity.Entities.Entity>`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.Entity> GetStartTiles();
```

- `private LegacyGenerateMapTiles(System.Boolean editorMode) : System.Void`  

```csharp
private System.Void LegacyGenerateMapTiles(System.Boolean editorMode);
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

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Areas.MapTileSystem+GenerateMapTilesJob`  
- `Game.Areas.MapTileSystem+TypeHandle`  

