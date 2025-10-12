# Game.Tools.TrafficRoutesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Boolean <routesVisible>k__BackingField`  
- `private Game.Common.ModificationBarrier2 m_ModificationBarrier`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Unity.Entities.EntityQuery m_LivePathQuery`  
- `private Unity.Entities.EntityQuery m_PathSourceQuery`  
- `private Unity.Entities.EntityQuery m_RouteConfigQuery`  
- `private System.Int32 m_UpdateFrameIndex`  
- `private Game.Tools.TrafficRoutesSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.Boolean routesVisible { get; set }`  

## Constructors

- `public TrafficRoutesSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tools.TrafficRoutesSystem+LivePathEntityData`  
- `Game.Tools.TrafficRoutesSystem+FillTargetMapJob`  
- `Game.Tools.TrafficRoutesSystem+FindPathSourcesJob`  
- `Game.Tools.TrafficRoutesSystem+UpdateLivePathsJob`  
- `Game.Tools.TrafficRoutesSystem+TypeHandle`  

