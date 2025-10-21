# Game.Routes.ValidationHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ValidationHelpers
{
    private static Unity.Mathematics.bool2 FindStopLanes(Game.Objects.Attached attached, Game.Prefabs.RouteConnectionData connectionData, Game.Tools.ValidationSystem+EntityData data);
    private static Game.Tools.ErrorType RouteConnectionToError(Game.Prefabs.RouteConnectionType type);
    public static System.Void ValidateRoute(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Prefabs.PrefabRef prefabRef, Unity.Entities.DynamicBuffer<Game.Routes.RouteWaypoint> waypoints, Unity.Entities.DynamicBuffer<Game.Routes.RouteSegment> segments, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    public static System.Void ValidateStop(System.Boolean editorMode, Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Objects.Attached attached, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
}
```


## Methods

- `private static FindStopLanes(Game.Objects.Attached attached, Game.Prefabs.RouteConnectionData connectionData, Game.Tools.ValidationSystem+EntityData data) : Unity.Mathematics.bool2`  

```csharp
private static Unity.Mathematics.bool2 FindStopLanes(Game.Objects.Attached attached, Game.Prefabs.RouteConnectionData connectionData, Game.Tools.ValidationSystem+EntityData data);
```

- `private static RouteConnectionToError(Game.Prefabs.RouteConnectionType type) : Game.Tools.ErrorType`  

```csharp
private static Game.Tools.ErrorType RouteConnectionToError(Game.Prefabs.RouteConnectionType type);
```

- `public static ValidateRoute(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Prefabs.PrefabRef prefabRef, Unity.Entities.DynamicBuffer<Game.Routes.RouteWaypoint> waypoints, Unity.Entities.DynamicBuffer<Game.Routes.RouteSegment> segments, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static System.Void ValidateRoute(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Prefabs.PrefabRef prefabRef, Unity.Entities.DynamicBuffer<Game.Routes.RouteWaypoint> waypoints, Unity.Entities.DynamicBuffer<Game.Routes.RouteSegment> segments, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
```

- `public static ValidateStop(System.Boolean editorMode, Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Objects.Attached attached, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static System.Void ValidateStop(System.Boolean editorMode, Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Objects.Attached attached, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
```


