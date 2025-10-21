# Game.Simulation.TouristFindTargetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TouristFindTargetSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_SeekerQuery;
    private Unity.Entities.ComponentTypeSet m_PathfindTypes;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Events.AddMeetingSystem m_AddMeetingSystem;
    private Unity.Collections.NativeQueue<Game.Simulation.TouristFindTargetSystem+HotelReserveAction> m_HotelReserveQueue;
    private Game.Simulation.TouristFindTargetSystem+TypeHandle __TypeHandle;

    public TouristFindTargetSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_SeekerQuery`  

```csharp
private Unity.Entities.EntityQuery m_SeekerQuery;
```

- `private Unity.Entities.ComponentTypeSet m_PathfindTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_PathfindTypes;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.Events.AddMeetingSystem m_AddMeetingSystem`  

```csharp
private Game.Events.AddMeetingSystem m_AddMeetingSystem;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.TouristFindTargetSystem+HotelReserveAction> m_HotelReserveQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.TouristFindTargetSystem+HotelReserveAction> m_HotelReserveQueue;
```

- `private Game.Simulation.TouristFindTargetSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TouristFindTargetSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TouristFindTargetSystem()`  

```csharp
public TouristFindTargetSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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


## Nested types

- `Game.Simulation.TouristFindTargetSystem+HotelReserveAction`  
- `Game.Simulation.TouristFindTargetSystem+TouristFindTargetJob`  
- `Game.Simulation.TouristFindTargetSystem+HotelReserveJob`  
- `Game.Simulation.TouristFindTargetSystem+TypeHandle`  

