# Game.Net.FixLaneObjectsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FixLaneObjectsSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Game.Net.LaneObjectUpdater m_LaneObjectUpdater;
    private Game.Net.FixLaneObjectsSystem+TypeHandle __TypeHandle;

    public FixLaneObjectsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Game.Net.LaneObjectUpdater m_LaneObjectUpdater`  

```csharp
private Game.Net.LaneObjectUpdater m_LaneObjectUpdater;
```

- `private Game.Net.FixLaneObjectsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.FixLaneObjectsSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public FixLaneObjectsSystem()`  

```csharp
public FixLaneObjectsSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Net.FixLaneObjectsSystem+CollectLaneObjectsJob`  
- `Game.Net.FixLaneObjectsSystem+FixLaneObjectsJob`  
- `Game.Net.FixLaneObjectsSystem+TypeHandle`  

