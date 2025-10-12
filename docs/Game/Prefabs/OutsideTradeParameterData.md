# Game.Prefabs.OutsideTradeParameterData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Fields

- `public System.Single m_ElectricityImportPrice`  
- `public System.Single m_ElectricityExportPrice`  
- `public System.Single m_WaterImportPrice`  
- `public System.Single m_WaterExportPrice`  
- `public System.Single m_WaterExportPollutionTolerance`  
- `public System.Single m_SewageExportPrice`  
- `public System.Single m_AirWeightMultiplier`  
- `public System.Single m_RoadWeightMultiplier`  
- `public System.Single m_TrainWeightMultiplier`  
- `public System.Single m_ShipWeightMultiplier`  
- `public System.Single m_AirDistanceMultiplier`  
- `public System.Single m_RoadDistanceMultiplier`  
- `public System.Single m_TrainDistanceMultiplier`  
- `public System.Single m_ShipDistanceMultiplier`  
- `public System.Single m_AmbulanceImportServiceFee`  
- `public System.Single m_HearseImportServiceFee`  
- `public System.Single m_FireEngineImportServiceFee`  
- `public System.Single m_GarbageImportServiceFee`  
- `public System.Single m_PoliceImportServiceFee`  
- `public System.Int32 m_OCServiceTradePopulationRange`  

## Methods

- `public Exportable(Game.City.PlayerResource resource) : System.Boolean`  
- `public GetDistanceCost(Game.Prefabs.OutsideConnectionTransferType type) : System.Single`  
- `private GetDistanceCostSingle(Game.Prefabs.OutsideConnectionTransferType type) : System.Single`  
- `public GetFee(Game.City.PlayerResource resource, System.Boolean export = False) : System.Single`  
- `public GetWeightCost(Game.Prefabs.OutsideConnectionTransferType type) : System.Single`  
- `private GetWeightCostSingle(Game.Prefabs.OutsideConnectionTransferType type) : System.Single`  
- `public Importable(Game.City.PlayerResource resource) : System.Boolean`  

