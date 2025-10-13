# Game.UI.InGame.TransportUIUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class TransportUIUtils
{
    private static System.Void AddCargo(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity);
    private static System.Void AddVehicleCargo(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity);
    public static Game.UI.InGame.UITransportLineData BuildTransportLine(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem m_PrefabSystem);
    public static System.Int32 CountLines(Unity.Collections.NativeArray<Game.UI.InGame.UITransportLineData> lines, Game.Prefabs.TransportType type, System.Boolean cargo);
    public static System.Single GetRouteLength(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public static System.Int32 GetRouteVehiclesCount(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity);
    public static Unity.Collections.NativeArray<Game.UI.InGame.UITransportLineData> GetSortedLines(Unity.Entities.EntityQuery query, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public static System.Int32 GetStopCount(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Methods

- `private static AddCargo(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity) : System.Void`  

```csharp
private static System.Void AddCargo(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity);
```

- `private static AddVehicleCargo(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity) : System.Void`  

```csharp
private static System.Void AddVehicleCargo(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity);
```

- `public static BuildTransportLine(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem m_PrefabSystem) : Game.UI.InGame.UITransportLineData`  

```csharp
public static Game.UI.InGame.UITransportLineData BuildTransportLine(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem m_PrefabSystem);
```

- `public static CountLines(Unity.Collections.NativeArray<Game.UI.InGame.UITransportLineData> lines, Game.Prefabs.TransportType type, System.Boolean cargo = False) : System.Int32`  

```csharp
public static System.Int32 CountLines(Unity.Collections.NativeArray<Game.UI.InGame.UITransportLineData> lines, Game.Prefabs.TransportType type, System.Boolean cargo);
```

- `public static GetRouteLength(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Single`  

```csharp
public static System.Single GetRouteLength(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public static GetRouteVehiclesCount(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity) : System.Int32`  

```csharp
public static System.Int32 GetRouteVehiclesCount(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity);
```

- `public static GetSortedLines(Unity.Entities.EntityQuery query, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : Unity.Collections.NativeArray<Game.UI.InGame.UITransportLineData>`  

```csharp
public static Unity.Collections.NativeArray<Game.UI.InGame.UITransportLineData> GetSortedLines(Unity.Entities.EntityQuery query, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
```

- `public static GetStopCount(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Int32`  

```csharp
public static System.Int32 GetStopCount(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


