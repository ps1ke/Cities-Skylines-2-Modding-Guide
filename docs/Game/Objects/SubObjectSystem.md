# Game.Objects.SubObjectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Common.ModificationBarrier2B m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_UpdateQuery`  
- `private Unity.Entities.EntityQuery m_TempQuery`  
- `private Unity.Entities.EntityQuery m_ContainerQuery`  
- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  
- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  
- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  
- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LoopErrorPrefabs`  
- `private Game.Objects.SubObjectSystem+TypeHandle __TypeHandle`  
- `private static const System.Int32 kMaxSubObjectDepth`  

## Constructors

- `public SubObjectSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private ShowLoopErrors() : System.Void`  

## Nested types

- `Game.Objects.SubObjectSystem+SubObjectOwnerData`  
- `Game.Objects.SubObjectSystem+SubObjectData`  
- `Game.Objects.SubObjectSystem+DeepSubObjectOwnerData`  
- `Game.Objects.SubObjectSystem+PlaceholderKey`  
- `Game.Objects.SubObjectSystem+UpdateSubObjectsData`  
- `Game.Objects.SubObjectSystem+CheckSubObjectOwnersJob`  
- `Game.Objects.SubObjectSystem+CollectSubObjectOwnersJob`  
- `Game.Objects.SubObjectSystem+FillIgnoreSetJob`  
- `Game.Objects.SubObjectSystem+UpdateSubObjectsJob`  
- `Game.Objects.SubObjectSystem+TypeHandle`  

