# Game.Debug.PathfindDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  
- `private Colossal.GizmosSystem m_GizmosSystem`  
- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Unity.Collections.NativeList<Game.Debug.PathfindDebugSystem+PathfindLine> m_PathfindLines`  
- `private Game.Debug.BaseDebugSystem+Option m_GraphOption`  
- `private Game.Debug.BaseDebugSystem+Option m_RestrictedOption`  
- `private Game.Debug.BaseDebugSystem+Option m_TimeCostOption`  
- `private Game.Debug.BaseDebugSystem+Option m_BehaviorCostOption`  
- `private Game.Debug.BaseDebugSystem+Option m_MoneyCostOption`  
- `private Game.Debug.BaseDebugSystem+Option m_ComfortCostOption`  
- `private Game.Debug.BaseDebugSystem+Option m_PathfindOption`  

## Constructors

- `public PathfindDebugSystem()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Debug.PathfindDebugSystem+PathfindLine`  
- `Game.Debug.PathfindDebugSystem+EdgeCountJob`  
- `Game.Debug.PathfindDebugSystem+PathfindEdgeGizmoJob`  
- `Game.Debug.PathfindDebugSystem+FillPathfindGizmoLinesJob`  
- `Game.Debug.PathfindDebugSystem+SetPathfindGizmoLineFlagsJob`  
- `Game.Debug.PathfindDebugSystem+PathfindLineGizmoJob`  

