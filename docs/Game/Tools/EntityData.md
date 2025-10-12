# Game.Tools.ValidationSystem+EntityData

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_Owner`  
- `public Unity.Entities.ComponentLookup<Game.Tools.Hidden> m_Hidden`  
- `public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_Temp`  
- `public Unity.Entities.ComponentLookup<Game.Common.Native> m_Native`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_Transform`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Elevation> m_ObjectElevation`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Secondary> m_Secondary`  
- `public Unity.Entities.ComponentLookup<Game.Objects.AssetStamp> m_AssetStamp`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Attachment> m_Attachment`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Attached> m_Attached`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Stack> m_Stack`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Building`  
- `public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_Upgrades`  
- `public Unity.Entities.ComponentLookup<Game.Net.Node> m_Node`  
- `public Unity.Entities.ComponentLookup<Game.Net.Edge> m_Edge`  
- `public Unity.Entities.ComponentLookup<Game.Net.EdgeGeometry> m_EdgeGeometry`  
- `public Unity.Entities.ComponentLookup<Game.Net.StartNodeGeometry> m_StartNodeGeometry`  
- `public Unity.Entities.ComponentLookup<Game.Net.EndNodeGeometry> m_EndNodeGeometry`  
- `public Unity.Entities.ComponentLookup<Game.Net.Composition> m_Composition`  
- `public Unity.Entities.ComponentLookup<Game.Net.Elevation> m_NetElevation`  
- `public Unity.Entities.ComponentLookup<Game.Net.Lane> m_Lane`  
- `public Unity.Entities.ComponentLookup<Game.Net.PedestrianLane> m_PedestrianLane`  
- `public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLane`  
- `public Unity.Entities.ComponentLookup<Game.Net.TrackLane> m_TrackLane`  
- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_Curve`  
- `public Unity.Entities.BufferLookup<Game.Net.SubLane> m_Lanes`  
- `public Unity.Entities.BufferLookup<Game.Net.ConnectedNode> m_ConnectedNodes`  
- `public Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> m_ConnectedEdges`  
- `public Unity.Entities.ComponentLookup<Game.Areas.Area> m_Area`  
- `public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes`  
- `public Unity.Entities.BufferLookup<Game.Areas.Triangle> m_AreaTriangles`  
- `public Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformation`  
- `public Unity.Entities.ComponentLookup<Game.Routes.Route> m_Route`  
- `public Unity.Entities.ComponentLookup<Game.Routes.Connected> m_RouteConnected`  
- `public Unity.Entities.ComponentLookup<Game.Events.OnFire> m_OnFire`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRef`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometry`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_PrefabBuilding`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableObjectData> m_PlaceableObject`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.StackData> m_PrefabStackData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetObjectData> m_PrefabNetObject`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableNetData> m_PlaceableNet`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_PrefabComposition`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetGeometryData> m_PrefabNetGeometry`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> m_PrefabAreaGeometry`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.StorageAreaData> m_PrefabStorageArea`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.LotData> m_PrefabLotData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.CarLaneData> m_CarLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.TrackLaneData> m_TrackLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.RouteConnectionData> m_RouteConnectionData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.TransportStopData> m_TransportStopData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.TransportLineData> m_TransportLineData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.WaterPumpingStationData> m_WaterPumpingStationData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.GroundWaterPoweredData> m_GroundWaterPoweredData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.TerraformingData> m_TerraformingData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ServiceUpgradeData> m_ServiceUpgradeData`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.NetCompositionArea> m_PrefabCompositionAreas`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.FixedNetElement> m_PrefabFixedElements`  

## Constructors

- `public EntityData(Unity.Entities.SystemBase system)`  

## Methods

- `public Update(Unity.Entities.SystemBase system) : System.Void`  

