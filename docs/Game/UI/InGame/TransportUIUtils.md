# Game.UI.InGame.TransportUIUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class static public  

**Base:** `System.Object`  

## Methods

- `private static AddCargo(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity) : System.Void`  
- `private static AddVehicleCargo(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity) : System.Void`  
- `public static BuildTransportLine(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem m_PrefabSystem) : Game.UI.InGame.UITransportLineData`  
- `public static CountLines(Unity.Collections.NativeArray<Game.UI.InGame.UITransportLineData> lines, Game.Prefabs.TransportType type, System.Boolean cargo = False) : System.Int32`  
- `public static GetRouteLength(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Single`  
- `public static GetRouteVehiclesCount(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity) : System.Int32`  
- `public static GetSortedLines(Unity.Entities.EntityQuery query, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : Unity.Collections.NativeArray<Game.UI.InGame.UITransportLineData>`  
- `public static GetStopCount(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Int32`  

