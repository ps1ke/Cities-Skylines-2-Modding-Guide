# Game.Simulation.AdjustElectricityConsumptionSystem+AdjustElectricityConsumptionJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct AdjustElectricityConsumptionJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.SharedComponentTypeHandle<Game.Simulation.UpdateFrame> m_UpdateFrameType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
    public Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_BuildingType;
    public Unity.Entities.ComponentTypeHandle<Game.City.CityServiceUpkeep> m_CityServiceType;
    public Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_UpgradeType;
    public Unity.Entities.ComponentTypeHandle<Game.Simulation.ElectricityBuildingConnection> m_BuildingConnectionType;
    public Unity.Entities.ComponentTypeHandle<Game.Areas.CurrentDistrict> m_CurrentDistrictType;
    public Unity.Entities.BufferTypeHandle<Game.Buildings.Renter> m_RenterType;
    public Unity.Entities.ComponentTypeHandle<Game.Buildings.Park> m_ParkType;
    public Unity.Entities.ComponentTypeHandle<Game.Buildings.StorageProperty> m_StoragePropertyType;
    public Unity.Entities.ComponentTypeHandle<Game.Buildings.ElectricityConsumer> m_ConsumerType;
    public Unity.Entities.BufferTypeHandle<Game.Buildings.Efficiency> m_EfficiencyType;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ConsumptionData> m_ServiceConsumption;
    public Unity.Entities.BufferLookup<Game.City.ServiceFee> m_Fees;
    public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizens;
    public Unity.Entities.BufferLookup<Game.Companies.Employee> m_Employees;
    public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableDatas;
    public Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_Citizens;
    public Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> m_DistrictModifiers;
    public Unity.Entities.ComponentLookup<Game.Simulation.ElectricityFlowEdge> m_FlowEdges;
    public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdatedEdges;
    public Game.Prefabs.ServiceFeeParameterData m_FeeParameters;
    public Game.Prefabs.BuildingEfficiencyParameterData m_EfficiencyParameters;
    public Game.Common.RandomSeed m_RandomSeed;
    public Unity.Entities.Entity m_City;
    public System.Single m_TemperatureMultiplier;
    public System.UInt32 m_UpdateFrameIndex;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Entities.SharedComponentTypeHandle<Game.Simulation.UpdateFrame> m_UpdateFrameType`  

```csharp
public Unity.Entities.SharedComponentTypeHandle<Game.Simulation.UpdateFrame> m_UpdateFrameType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_BuildingType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_BuildingType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.City.CityServiceUpkeep> m_CityServiceType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.City.CityServiceUpkeep> m_CityServiceType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_UpgradeType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_UpgradeType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Simulation.ElectricityBuildingConnection> m_BuildingConnectionType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Simulation.ElectricityBuildingConnection> m_BuildingConnectionType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Areas.CurrentDistrict> m_CurrentDistrictType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Areas.CurrentDistrict> m_CurrentDistrictType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Buildings.Renter> m_RenterType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Buildings.Renter> m_RenterType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.Park> m_ParkType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Buildings.Park> m_ParkType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.StorageProperty> m_StoragePropertyType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Buildings.StorageProperty> m_StoragePropertyType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.ElectricityConsumer> m_ConsumerType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Buildings.ElectricityConsumer> m_ConsumerType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Buildings.Efficiency> m_EfficiencyType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Buildings.Efficiency> m_EfficiencyType;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ConsumptionData> m_ServiceConsumption`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ConsumptionData> m_ServiceConsumption;
```

- `public Unity.Entities.BufferLookup<Game.City.ServiceFee> m_Fees`  

```csharp
public Unity.Entities.BufferLookup<Game.City.ServiceFee> m_Fees;
```

- `public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizens`  

```csharp
public Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizens;
```

- `public Unity.Entities.BufferLookup<Game.Companies.Employee> m_Employees`  

```csharp
public Unity.Entities.BufferLookup<Game.Companies.Employee> m_Employees;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_Citizens`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_Citizens;
```

- `public Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> m_DistrictModifiers`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> m_DistrictModifiers;
```

- `public Unity.Entities.ComponentLookup<Game.Simulation.ElectricityFlowEdge> m_FlowEdges`  

```csharp
public Unity.Entities.ComponentLookup<Game.Simulation.ElectricityFlowEdge> m_FlowEdges;
```

- `public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdatedEdges`  

```csharp
public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdatedEdges;
```

- `public Game.Prefabs.ServiceFeeParameterData m_FeeParameters`  

```csharp
public Game.Prefabs.ServiceFeeParameterData m_FeeParameters;
```

- `public Game.Prefabs.BuildingEfficiencyParameterData m_EfficiencyParameters`  

```csharp
public Game.Prefabs.BuildingEfficiencyParameterData m_EfficiencyParameters;
```

- `public Game.Common.RandomSeed m_RandomSeed`  

```csharp
public Game.Common.RandomSeed m_RandomSeed;
```

- `public Unity.Entities.Entity m_City`  

```csharp
public Unity.Entities.Entity m_City;
```

- `public System.Single m_TemperatureMultiplier`  

```csharp
public System.Single m_TemperatureMultiplier;
```

- `public System.UInt32 m_UpdateFrameIndex`  

```csharp
public System.UInt32 m_UpdateFrameIndex;
```


## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```

- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```


