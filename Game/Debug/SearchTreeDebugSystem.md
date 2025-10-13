# Game.Debug.SearchTreeDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

## Code

```csharp
public class SearchTreeDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Zones.SearchSystem m_ZoneSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Routes.SearchSystem m_RouteSearchSystem;
    private Game.Effects.SearchSystem m_EffectSearchSystem;
    private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_StaticObjectOption;
    private Game.Debug.BaseDebugSystem+Option m_MovingObjectOption;
    private Game.Debug.BaseDebugSystem+Option m_NetOption;
    private Game.Debug.BaseDebugSystem+Option m_LaneOption;
    private Game.Debug.BaseDebugSystem+Option m_ZoneOption;
    private Game.Debug.BaseDebugSystem+Option m_AreaOption;
    private Game.Debug.BaseDebugSystem+Option m_RouteOption;
    private Game.Debug.BaseDebugSystem+Option m_EffectOption;
    private Game.Debug.BaseDebugSystem+Option m_LocalEffectOption;

    public SearchTreeDebugSystem();

    private Unity.Jobs.JobHandle AreaSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
    private Unity.Jobs.JobHandle EffectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
    private Unity.Jobs.JobHandle LaneSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
    private Unity.Jobs.JobHandle LocalEffectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
    private Unity.Jobs.JobHandle MovingObjectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
    private Unity.Jobs.JobHandle NetSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
    protected virtual System.Void OnCreate();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle RouteSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
    private Unity.Jobs.JobHandle StaticObjectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
    private Unity.Jobs.JobHandle ZoneSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
}
```


## Fields

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  

```csharp
private Game.Zones.SearchSystem m_ZoneSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Routes.SearchSystem m_RouteSearchSystem`  

```csharp
private Game.Routes.SearchSystem m_RouteSearchSystem;
```

- `private Game.Effects.SearchSystem m_EffectSearchSystem`  

```csharp
private Game.Effects.SearchSystem m_EffectSearchSystem;
```

- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  

```csharp
private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_StaticObjectOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_StaticObjectOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_MovingObjectOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_MovingObjectOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_NetOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_NetOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_LaneOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_LaneOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ZoneOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ZoneOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_AreaOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_AreaOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_RouteOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_RouteOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_EffectOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_EffectOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_LocalEffectOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_LocalEffectOption;
```


## Constructors

- `public SearchTreeDebugSystem()`  

```csharp
public SearchTreeDebugSystem();
```


## Methods

- `private AreaSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle AreaSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
```

- `private EffectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle EffectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
```

- `private LaneSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle LaneSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
```

- `private LocalEffectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle LocalEffectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
```

- `private MovingObjectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle MovingObjectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
```

- `private NetSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle NetSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```

- `private RouteSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle RouteSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
```

- `private StaticObjectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle StaticObjectSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
```

- `private ZoneSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle ZoneSearchTreeDebug(Unity.Jobs.JobHandle inputDeps, Colossal.Mathematics.Bounds3 bounds);
```


## Nested types

- `Game.Debug.SearchTreeDebugSystem+NativeQuadTreeGizmoJob<TItem, TBounds, TIterator>`  
- `Game.Debug.SearchTreeDebugSystem+Bounds2DebugIterator<TItem>`  
- `Game.Debug.SearchTreeDebugSystem+LocalEffectDebugIterator`  

