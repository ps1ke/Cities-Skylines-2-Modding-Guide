# Game.Buildings.RoadConnectionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RoadConnectionSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4B m_ModificationBarrier;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Audio.AudioManager m_AudioManager;
    private Unity.Entities.EntityQuery m_ModificationQuery;
    private Unity.Entities.EntityQuery m_UpdatedNetQuery;
    private Unity.Entities.EntityQuery m_TrafficConfigQuery;
    private Unity.Entities.EntityQuery m_BuildingConfigQuery;
    private Unity.Entities.EntityQuery m_ConnectionQuery;
    private Unity.Entities.EntityArchetype m_RoadConnectionEventArchetype;
    private Unity.Entities.ComponentTypeSet m_AppliedTypes;
    private Game.Buildings.RoadConnectionSystem+TypeHandle __TypeHandle;

    public RoadConnectionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Void CheckDistance(Game.Net.EdgeGeometry edgeGeometry, Game.Net.EdgeNodeGeometry startGeometry, Game.Net.EdgeNodeGeometry endGeometry, Unity.Mathematics.float3 position, System.Boolean canBeOnRoad, System.Single& maxDistance);
    private static System.Void CheckDistance(Colossal.Mathematics.Bezier4x3 curve1, Colossal.Mathematics.Bezier4x3 curve2, Unity.Mathematics.float3 position, System.Single& maxDistance);
    private static System.Void CheckDistance(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, System.Single& maxDistance);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4B m_ModificationBarrier;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Unity.Entities.EntityQuery m_ModificationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModificationQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedNetQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedNetQuery;
```

- `private Unity.Entities.EntityQuery m_TrafficConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_TrafficConfigQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingConfigQuery;
```

- `private Unity.Entities.EntityQuery m_ConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConnectionQuery;
```

- `private Unity.Entities.EntityArchetype m_RoadConnectionEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_RoadConnectionEventArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AppliedTypes;
```

- `private Game.Buildings.RoadConnectionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.RoadConnectionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RoadConnectionSystem()`  

```csharp
public RoadConnectionSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private static CheckDistance(Game.Net.EdgeGeometry edgeGeometry, Game.Net.EdgeNodeGeometry startGeometry, Game.Net.EdgeNodeGeometry endGeometry, Unity.Mathematics.float3 position, System.Boolean canBeOnRoad, System.Single& maxDistance) : System.Void`  

```csharp
private static System.Void CheckDistance(Game.Net.EdgeGeometry edgeGeometry, Game.Net.EdgeNodeGeometry startGeometry, Game.Net.EdgeNodeGeometry endGeometry, Unity.Mathematics.float3 position, System.Boolean canBeOnRoad, System.Single& maxDistance);
```

- `private static CheckDistance(Colossal.Mathematics.Bezier4x3 curve1, Colossal.Mathematics.Bezier4x3 curve2, Unity.Mathematics.float3 position, System.Single& maxDistance) : System.Void`  

```csharp
private static System.Void CheckDistance(Colossal.Mathematics.Bezier4x3 curve1, Colossal.Mathematics.Bezier4x3 curve2, Unity.Mathematics.float3 position, System.Single& maxDistance);
```

- `private static CheckDistance(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, System.Single& maxDistance) : System.Void`  

```csharp
private static System.Void CheckDistance(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, System.Single& maxDistance);
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

- `Game.Buildings.RoadConnectionSystem+CheckRoadConnectionJob`  
- `Game.Buildings.RoadConnectionSystem+FillReplacementListJob`  
- `Game.Buildings.RoadConnectionSystem+ReplaceRoad`  
- `Game.Buildings.RoadConnectionSystem+FindRoadConnectionJob`  
- `Game.Buildings.RoadConnectionSystem+ReplaceRoadConnectionJob`  
- `Game.Buildings.RoadConnectionSystem+ConnectionLaneKey`  
- `Game.Buildings.RoadConnectionSystem+SpawnLocationData`  
- `Game.Buildings.RoadConnectionSystem+UpdateSecondaryLanesJob`  
- `Game.Buildings.RoadConnectionSystem+TypeHandle`  

