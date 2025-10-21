# Game.Pathfind.LanePoliciesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LanePoliciesSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_PolicyModifyQuery;
    private Unity.Entities.EntityQuery m_LaneOwnerQuery;
    private Unity.Entities.EntityQuery m_CarLaneQuery;
    private Unity.Entities.EntityQuery m_ParkingLaneQuery;
    private Game.Pathfind.LanePoliciesSystem+TypeHandle __TypeHandle;

    public LanePoliciesSystem();

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

- `private Unity.Entities.EntityQuery m_PolicyModifyQuery`  

```csharp
private Unity.Entities.EntityQuery m_PolicyModifyQuery;
```

- `private Unity.Entities.EntityQuery m_LaneOwnerQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneOwnerQuery;
```

- `private Unity.Entities.EntityQuery m_CarLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_CarLaneQuery;
```

- `private Unity.Entities.EntityQuery m_ParkingLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkingLaneQuery;
```

- `private Game.Pathfind.LanePoliciesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Pathfind.LanePoliciesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LanePoliciesSystem()`  

```csharp
public LanePoliciesSystem();
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

- `Game.Pathfind.LanePoliciesSystem+LaneCheckMask`  
- `Game.Pathfind.LanePoliciesSystem+CheckDistrictLanesJob`  
- `Game.Pathfind.LanePoliciesSystem+CheckBuildingLanesJob`  
- `Game.Pathfind.LanePoliciesSystem+TypeHandle`  

