# Game.Debug.PathfindDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

## Code

```csharp
public class PathfindDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Unity.Collections.NativeList<Game.Debug.PathfindDebugSystem+PathfindLine> m_PathfindLines;
    private Game.Debug.BaseDebugSystem+Option m_GraphOption;
    private Game.Debug.BaseDebugSystem+Option m_RestrictedOption;
    private Game.Debug.BaseDebugSystem+Option m_TimeCostOption;
    private Game.Debug.BaseDebugSystem+Option m_BehaviorCostOption;
    private Game.Debug.BaseDebugSystem+Option m_MoneyCostOption;
    private Game.Debug.BaseDebugSystem+Option m_ComfortCostOption;
    private Game.Debug.BaseDebugSystem+Option m_PathfindOption;

    public PathfindDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Unity.Collections.NativeList<Game.Debug.PathfindDebugSystem+PathfindLine> m_PathfindLines`  

```csharp
private Unity.Collections.NativeList<Game.Debug.PathfindDebugSystem+PathfindLine> m_PathfindLines;
```

- `private Game.Debug.BaseDebugSystem+Option m_GraphOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_GraphOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_RestrictedOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_RestrictedOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_TimeCostOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_TimeCostOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_BehaviorCostOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_BehaviorCostOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_MoneyCostOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_MoneyCostOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ComfortCostOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ComfortCostOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_PathfindOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_PathfindOption;
```


## Constructors

- `public PathfindDebugSystem()`  

```csharp
public PathfindDebugSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Debug.PathfindDebugSystem+PathfindLine`  
- `Game.Debug.PathfindDebugSystem+EdgeCountJob`  
- `Game.Debug.PathfindDebugSystem+PathfindEdgeGizmoJob`  
- `Game.Debug.PathfindDebugSystem+FillPathfindGizmoLinesJob`  
- `Game.Debug.PathfindDebugSystem+SetPathfindGizmoLineFlagsJob`  
- `Game.Debug.PathfindDebugSystem+PathfindLineGizmoJob`  

