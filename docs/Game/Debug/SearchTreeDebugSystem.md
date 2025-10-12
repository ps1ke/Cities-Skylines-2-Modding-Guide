# Game.Debug.SearchTreeDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

## Fields

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Routes.SearchSystem m_RouteSearchSystem`  
- `private Game.Effects.SearchSystem m_EffectSearchSystem`  
- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  
- `private Colossal.GizmosSystem m_GizmosSystem`  
- `private Game.Debug.BaseDebugSystem+Option m_StaticObjectOption`  
- `private Game.Debug.BaseDebugSystem+Option m_MovingObjectOption`  
- `private Game.Debug.BaseDebugSystem+Option m_NetOption`  
- `private Game.Debug.BaseDebugSystem+Option m_LaneOption`  
- `private Game.Debug.BaseDebugSystem+Option m_ZoneOption`  
- `private Game.Debug.BaseDebugSystem+Option m_AreaOption`  
- `private Game.Debug.BaseDebugSystem+Option m_RouteOption`  
- `private Game.Debug.BaseDebugSystem+Option m_EffectOption`  
- `private Game.Debug.BaseDebugSystem+Option m_LocalEffectOption`  

## Constructors

- `public SearchTreeDebugSystem()`  

## Methods

- `private AreaSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  
- `private EffectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  
- `private LaneSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  
- `private LocalEffectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  
- `private MovingObjectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  
- `private NetSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private RouteSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  
- `private StaticObjectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  
- `private ZoneSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Debug.SearchTreeDebugSystem+NativeQuadTreeGizmoJob<TItem, TBounds, TIterator>`  
- `Game.Debug.SearchTreeDebugSystem+Bounds2DebugIterator<TItem>`  
- `Game.Debug.SearchTreeDebugSystem+LocalEffectDebugIterator`  

