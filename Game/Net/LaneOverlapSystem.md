# Game.Net.LaneOverlapSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneOverlapSystem : Game.GameSystemBase
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.EntityQuery m_UpdatedOwnersQuery;
    private Unity.Entities.EntityQuery m_UpdatedLanesQuery;
    private Unity.Entities.EntityQuery m_AllOwnersQuery;
    private Unity.Entities.EntityQuery m_AllLanesQuery;
    private System.Boolean m_Loaded;
    private Game.Net.LaneOverlapSystem+TypeHandle __TypeHandle;

    public LaneOverlapSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedOwnersQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedOwnersQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedLanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedLanesQuery;
```

- `private Unity.Entities.EntityQuery m_AllOwnersQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllOwnersQuery;
```

- `private Unity.Entities.EntityQuery m_AllLanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllLanesQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Net.LaneOverlapSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.LaneOverlapSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneOverlapSystem()`  

```csharp
public LaneOverlapSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Net.LaneOverlapSystem+AddNonUpdatedEdgesJob`  
- `Game.Net.LaneOverlapSystem+UpdateLaneFlagsJob`  
- `Game.Net.LaneOverlapSystem+LaneSourceData`  
- `Game.Net.LaneOverlapSystem+LaneTargetData`  
- `Game.Net.LaneOverlapSystem+CollectLaneDirectionsJob`  
- `Game.Net.LaneOverlapSystem+OverlapData`  
- `Game.Net.LaneOverlapSystem+ApplyExtraOverlapsJob`  
- `Game.Net.LaneOverlapSystem+SortLaneOverlapsJob`  
- `Game.Net.LaneOverlapSystem+UpdateLaneOverlapsJob`  
- `Game.Net.LaneOverlapSystem+TypeHandle`  

