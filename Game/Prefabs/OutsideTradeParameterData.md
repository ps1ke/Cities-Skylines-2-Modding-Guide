# Game.Prefabs.OutsideTradeParameterData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct OutsideTradeParameterData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public System.Single m_ElectricityImportPrice;
    public System.Single m_ElectricityExportPrice;
    public System.Single m_WaterImportPrice;
    public System.Single m_WaterExportPrice;
    public System.Single m_WaterExportPollutionTolerance;
    public System.Single m_SewageExportPrice;
    public System.Single m_AirWeightMultiplier;
    public System.Single m_RoadWeightMultiplier;
    public System.Single m_TrainWeightMultiplier;
    public System.Single m_ShipWeightMultiplier;
    public System.Single m_AirDistanceMultiplier;
    public System.Single m_RoadDistanceMultiplier;
    public System.Single m_TrainDistanceMultiplier;
    public System.Single m_ShipDistanceMultiplier;
    public System.Single m_AmbulanceImportServiceFee;
    public System.Single m_HearseImportServiceFee;
    public System.Single m_FireEngineImportServiceFee;
    public System.Single m_GarbageImportServiceFee;
    public System.Single m_PoliceImportServiceFee;
    public System.Int32 m_OCServiceTradePopulationRange;

    public System.Boolean Exportable(Game.City.PlayerResource resource);
    public System.Single GetDistanceCost(Game.Prefabs.OutsideConnectionTransferType type);
    private System.Single GetDistanceCostSingle(Game.Prefabs.OutsideConnectionTransferType type);
    public System.Single GetFee(Game.City.PlayerResource resource, System.Boolean export);
    public System.Single GetWeightCost(Game.Prefabs.OutsideConnectionTransferType type);
    private System.Single GetWeightCostSingle(Game.Prefabs.OutsideConnectionTransferType type);
    public System.Boolean Importable(Game.City.PlayerResource resource);
}
```


## Fields

- `public System.Single m_ElectricityImportPrice`  

```csharp
public System.Single m_ElectricityImportPrice;
```

- `public System.Single m_ElectricityExportPrice`  

```csharp
public System.Single m_ElectricityExportPrice;
```

- `public System.Single m_WaterImportPrice`  

```csharp
public System.Single m_WaterImportPrice;
```

- `public System.Single m_WaterExportPrice`  

```csharp
public System.Single m_WaterExportPrice;
```

- `public System.Single m_WaterExportPollutionTolerance`  

```csharp
public System.Single m_WaterExportPollutionTolerance;
```

- `public System.Single m_SewageExportPrice`  

```csharp
public System.Single m_SewageExportPrice;
```

- `public System.Single m_AirWeightMultiplier`  

```csharp
public System.Single m_AirWeightMultiplier;
```

- `public System.Single m_RoadWeightMultiplier`  

```csharp
public System.Single m_RoadWeightMultiplier;
```

- `public System.Single m_TrainWeightMultiplier`  

```csharp
public System.Single m_TrainWeightMultiplier;
```

- `public System.Single m_ShipWeightMultiplier`  

```csharp
public System.Single m_ShipWeightMultiplier;
```

- `public System.Single m_AirDistanceMultiplier`  

```csharp
public System.Single m_AirDistanceMultiplier;
```

- `public System.Single m_RoadDistanceMultiplier`  

```csharp
public System.Single m_RoadDistanceMultiplier;
```

- `public System.Single m_TrainDistanceMultiplier`  

```csharp
public System.Single m_TrainDistanceMultiplier;
```

- `public System.Single m_ShipDistanceMultiplier`  

```csharp
public System.Single m_ShipDistanceMultiplier;
```

- `public System.Single m_AmbulanceImportServiceFee`  

```csharp
public System.Single m_AmbulanceImportServiceFee;
```

- `public System.Single m_HearseImportServiceFee`  

```csharp
public System.Single m_HearseImportServiceFee;
```

- `public System.Single m_FireEngineImportServiceFee`  

```csharp
public System.Single m_FireEngineImportServiceFee;
```

- `public System.Single m_GarbageImportServiceFee`  

```csharp
public System.Single m_GarbageImportServiceFee;
```

- `public System.Single m_PoliceImportServiceFee`  

```csharp
public System.Single m_PoliceImportServiceFee;
```

- `public System.Int32 m_OCServiceTradePopulationRange`  

```csharp
public System.Int32 m_OCServiceTradePopulationRange;
```


## Methods

- `public Exportable(Game.City.PlayerResource resource) : System.Boolean`  

```csharp
public System.Boolean Exportable(Game.City.PlayerResource resource);
```

- `public GetDistanceCost(Game.Prefabs.OutsideConnectionTransferType type) : System.Single`  

```csharp
public System.Single GetDistanceCost(Game.Prefabs.OutsideConnectionTransferType type);
```

- `private GetDistanceCostSingle(Game.Prefabs.OutsideConnectionTransferType type) : System.Single`  

```csharp
private System.Single GetDistanceCostSingle(Game.Prefabs.OutsideConnectionTransferType type);
```

- `public GetFee(Game.City.PlayerResource resource, System.Boolean export = False) : System.Single`  

```csharp
public System.Single GetFee(Game.City.PlayerResource resource, System.Boolean export);
```

- `public GetWeightCost(Game.Prefabs.OutsideConnectionTransferType type) : System.Single`  

```csharp
public System.Single GetWeightCost(Game.Prefabs.OutsideConnectionTransferType type);
```

- `private GetWeightCostSingle(Game.Prefabs.OutsideConnectionTransferType type) : System.Single`  

```csharp
private System.Single GetWeightCostSingle(Game.Prefabs.OutsideConnectionTransferType type);
```

- `public Importable(Game.City.PlayerResource resource) : System.Boolean`  

```csharp
public System.Boolean Importable(Game.City.PlayerResource resource);
```


