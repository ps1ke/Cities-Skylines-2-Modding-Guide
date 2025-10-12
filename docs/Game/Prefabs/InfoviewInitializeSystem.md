# Game.Prefabs.InfoviewInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_NewInfoviewQuery`  
- `private Unity.Entities.EntityQuery m_AllInfoviewQuery`  
- `private Unity.Entities.EntityQuery m_AllInfomodeQuery`  
- `private Unity.Entities.EntityQuery m_NewPlaceableQuery`  
- `private Unity.Entities.EntityQuery m_AllPlaceableQuery`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Prefabs.InfoviewInitializeSystem+TypeHandle __TypeHandle`  
- `private static const System.Int32 TYPE_PRIORITY`  
- `private static const System.Int32 PRIMARY_REQUIREMENT_PRIORITY`  
- `private static const System.Int32 SECONDARY_REQUIREMENT_PRIORITY`  
- `private static const System.Int32 PRIMARY_EFFECT_PRIORITY`  
- `private static const System.Int32 SECONDARY_EFFECT_PRIORITY`  

## Properties

- `public System.Collections.Generic.IEnumerable<Game.Prefabs.InfoviewPrefab> infoviews { get }`  
- `public System.Collections.Generic.IEnumerable<Game.Prefabs.InfomodePrefab> infomodes { get }`  

## Constructors

- `public InfoviewInitializeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private FindInfoviews(Unity.Jobs.JobHandle inputDeps, Unity.Entities.EntityQuery infoviewQuery, Unity.Entities.EntityQuery infomodeQuery, Unity.Entities.EntityQuery objectQuery) : Unity.Jobs.JobHandle`  
- `private InitializeInfoviews(Unity.Jobs.JobHandle inputDeps, Unity.Entities.EntityQuery infoviewGroup, Unity.Entities.EntityQuery infomodeGroup) : Unity.Jobs.JobHandle`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Prefabs.InfoviewInitializeSystem+InfoModeData`  
- `Game.Prefabs.InfoviewInitializeSystem+FindInfoviewJob`  
- `Game.Prefabs.InfoviewInitializeSystem+PollutionType`  
- `Game.Prefabs.InfoviewInitializeSystem+WaterType`  
- `Game.Prefabs.InfoviewInitializeSystem+InfoviewBufferData`  
- `Game.Prefabs.InfoviewInitializeSystem+FindSubInfoviewJob`  
- `Game.Prefabs.InfoviewInitializeSystem+AssignInfoviewJob`  
- `Game.Prefabs.InfoviewInitializeSystem+TypeHandle`  
- `Game.Prefabs.InfoviewInitializeSystem+<get___infomodes_F6CD08E>d__30`  
- `Game.Prefabs.InfoviewInitializeSystem+<get___infoviews_5966D7E4>d__28`  
- `Game.Prefabs.InfoviewInitializeSystem+<get_infomodes>d__11`  
- `Game.Prefabs.InfoviewInitializeSystem+<get_infoviews>d__9`  

