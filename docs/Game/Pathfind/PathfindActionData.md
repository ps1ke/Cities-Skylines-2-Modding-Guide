# Game.Pathfind.PathfindActionData

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Fields

- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathTarget> m_StartTargets`  
- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathTarget> m_EndTargets`  
- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathfindResult> m_Result`  
- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathfindPath> m_Path`  
- `public Game.Pathfind.PathfindParameters m_Parameters`  
- `public Game.Pathfind.SetupTargetType m_OriginType`  
- `public Game.Pathfind.SetupTargetType m_DestinationType`  
- `public Game.Pathfind.PathfindActionState m_State`  

## Constructors

- `public PathfindActionData(System.Int32 startCount, System.Int32 endCount, Unity.Collections.Allocator allocator, Game.Pathfind.PathfindParameters parameters, Game.Pathfind.SetupTargetType originType, Game.Pathfind.SetupTargetType destinationType)`  

## Methods

- `public Dispose() : System.Void`  

