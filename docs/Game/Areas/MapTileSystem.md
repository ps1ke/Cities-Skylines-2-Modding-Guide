# Game.Areas.MapTileSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Unity.Entities.EntityQuery m_MapTileQuery`  
- `private Unity.Entities.EntityQuery m_DeletedMapTileQuery`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_StartTiles`  
- `private Game.Areas.MapTileSystem+TypeHandle __TypeHandle`  
- `private static const System.Int32 LEGACY_GRID_WIDTH`  
- `private static const System.Int32 LEGACY_GRID_LENGTH`  
- `private static const System.Single LEGACY_CELL_SIZE`  

## Constructors

- `public MapTileSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private AddOwner(Unity.Mathematics.int2 tile, Unity.Collections.NativeArray<Unity.Entities.Entity> entities) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetStartTiles() : Unity.Collections.NativeList<Unity.Entities.Entity>`  
- `private LegacyGenerateMapTiles(System.Boolean editorMode) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Areas.MapTileSystem+GenerateMapTilesJob`  
- `Game.Areas.MapTileSystem+TypeHandle`  

