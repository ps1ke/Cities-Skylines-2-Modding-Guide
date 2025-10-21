# Game.Simulation.TelecomCoverageSystem+TelecomCoverageJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct TelecomCoverageJob : Unity.Jobs.IJob
{
    public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_DensityChunks;
    public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_FacilityChunks;
    public Game.Simulation.TerrainHeightData m_TerrainHeightData;
    public Unity.Entities.Entity m_City;
    public System.Boolean m_Preview;
    public Unity.Collections.NativeArray<Game.Simulation.TelecomCoverage> m_TelecomCoverage;
    public Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_TelecomStatus;
    public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_TransformType;
    public Unity.Entities.ComponentTypeHandle<Game.Buildings.PropertyRenter> m_PropertyRenterType;
    public Unity.Entities.ComponentTypeHandle<Game.Buildings.TelecomFacility> m_TelecomFacilityType;
    public Unity.Entities.BufferTypeHandle<Game.Buildings.Efficiency> m_BuildingEfficiencyType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
    public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_TempType;
    public Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType;
    public Unity.Entities.BufferTypeHandle<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenType;
    public Unity.Entities.BufferTypeHandle<Game.Companies.Employee> m_EmployeeType;
    public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
    public Unity.Entities.ComponentLookup<Game.Buildings.TelecomFacility> m_TelecomFacilityData;
    public Unity.Entities.BufferLookup<Game.Buildings.Efficiency> m_BuildingEfficiencyData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_ObjectGeometryData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.TelecomFacilityData> m_PrefabTelecomFacilityData;
    public Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers;

    private System.Void AddDensity(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, Unity.Entities.ArchetypeChunk chunk);
    private System.Void AddDensity(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, System.Int32 density, Unity.Mathematics.float3 position);
    private System.Void AddNetworkCapacity(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeList<System.Single> signalStrengths, Unity.Entities.ArchetypeChunk chunk, System.Int32& arrayIndex, Game.Simulation.TelecomStatus& status, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers);
    private System.Void AddNetworkCapacity(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, System.Single capacity);
    private System.Void AddSignalStrengths(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max);
    private System.Void CalculateCellSignalStrength(Unity.Collections.NativeArray<System.Single> obstructSlopes, Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 cell, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, System.Single range, Unity.Mathematics.float3 position);
    private System.Single CalculateNetworkUsers(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max);
    private System.Void CalculateSignalStrength(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeArray<System.Single> obstructSlopes, Unity.Collections.NativeList<System.Single> signalStrengths, Unity.Entities.ArchetypeChunk chunk, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers);
    private System.Void CalculateSignalStrength(Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, System.Single range, Unity.Mathematics.float3 position);
    private System.Single CalculateSignalStrength(System.Single distance, System.Single range);
    private System.Void CalculateTelecomCoverage(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData);
    private System.Single CalculateTelecomQuality(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData);
    public System.Void Execute();
    private System.Single GetEfficiencyFactor(Unity.Collections.NativeArray<Game.Buildings.TelecomFacility> telecomFacilities, Unity.Collections.NativeArray<Game.Tools.Temp> temps, Unity.Entities.BufferAccessor<Game.Buildings.Efficiency> efficiencyAccessor, System.Int32 i);
    private System.Void ResetObstructAngles(Unity.Collections.NativeArray<System.Single> obstructAngles, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max);
}
```


## Fields

- `public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_DensityChunks`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_DensityChunks;
```

- `public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_FacilityChunks`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_FacilityChunks;
```

- `public Game.Simulation.TerrainHeightData m_TerrainHeightData`  

```csharp
public Game.Simulation.TerrainHeightData m_TerrainHeightData;
```

- `public Unity.Entities.Entity m_City`  

```csharp
public Unity.Entities.Entity m_City;
```

- `public System.Boolean m_Preview`  

```csharp
public System.Boolean m_Preview;
```

- `public Unity.Collections.NativeArray<Game.Simulation.TelecomCoverage> m_TelecomCoverage`  

```csharp
public Unity.Collections.NativeArray<Game.Simulation.TelecomCoverage> m_TelecomCoverage;
```

- `public Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_TelecomStatus`  

```csharp
public Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_TelecomStatus;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_TransformType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_TransformType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.PropertyRenter> m_PropertyRenterType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Buildings.PropertyRenter> m_PropertyRenterType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.TelecomFacility> m_TelecomFacilityType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Buildings.TelecomFacility> m_TelecomFacilityType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Buildings.Efficiency> m_BuildingEfficiencyType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Buildings.Efficiency> m_BuildingEfficiencyType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_TempType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_TempType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Companies.Employee> m_EmployeeType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Companies.Employee> m_EmployeeType;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.TelecomFacility> m_TelecomFacilityData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.TelecomFacility> m_TelecomFacilityData;
```

- `public Unity.Entities.BufferLookup<Game.Buildings.Efficiency> m_BuildingEfficiencyData`  

```csharp
public Unity.Entities.BufferLookup<Game.Buildings.Efficiency> m_BuildingEfficiencyData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_ObjectGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_ObjectGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.TelecomFacilityData> m_PrefabTelecomFacilityData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.TelecomFacilityData> m_PrefabTelecomFacilityData;
```

- `public Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers`  

```csharp
public Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers;
```


## Methods

- `private AddDensity(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, Unity.Entities.ArchetypeChunk chunk) : System.Void`  

```csharp
private System.Void AddDensity(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, Unity.Entities.ArchetypeChunk chunk);
```

- `private AddDensity(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, System.Int32 density, Unity.Mathematics.float3 position) : System.Void`  

```csharp
private System.Void AddDensity(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, System.Int32 density, Unity.Mathematics.float3 position);
```

- `private AddNetworkCapacity(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeList<System.Single> signalStrengths, Unity.Entities.ArchetypeChunk chunk, System.Int32& arrayIndex, Game.Simulation.TelecomStatus& status, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers) : System.Void`  

```csharp
private System.Void AddNetworkCapacity(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeList<System.Single> signalStrengths, Unity.Entities.ArchetypeChunk chunk, System.Int32& arrayIndex, Game.Simulation.TelecomStatus& status, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers);
```

- `private AddNetworkCapacity(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, System.Single capacity) : System.Void`  

```csharp
private System.Void AddNetworkCapacity(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, System.Single capacity);
```

- `private AddSignalStrengths(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max) : System.Void`  

```csharp
private System.Void AddSignalStrengths(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max);
```

- `private CalculateCellSignalStrength(Unity.Collections.NativeArray<System.Single> obstructSlopes, Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 cell, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, System.Single range, Unity.Mathematics.float3 position) : System.Void`  

```csharp
private System.Void CalculateCellSignalStrength(Unity.Collections.NativeArray<System.Single> obstructSlopes, Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 cell, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, System.Single range, Unity.Mathematics.float3 position);
```

- `private CalculateNetworkUsers(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max) : System.Single`  

```csharp
private System.Single CalculateNetworkUsers(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max);
```

- `private CalculateSignalStrength(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeArray<System.Single> obstructSlopes, Unity.Collections.NativeList<System.Single> signalStrengths, Unity.Entities.ArchetypeChunk chunk, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers) : System.Void`  

```csharp
private System.Void CalculateSignalStrength(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeArray<System.Single> obstructSlopes, Unity.Collections.NativeList<System.Single> signalStrengths, Unity.Entities.ArchetypeChunk chunk, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers);
```

- `private CalculateSignalStrength(Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, System.Single range, Unity.Mathematics.float3 position) : System.Void`  

```csharp
private System.Void CalculateSignalStrength(Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, System.Single range, Unity.Mathematics.float3 position);
```

- `private CalculateSignalStrength(System.Single distance, System.Single range) : System.Single`  

```csharp
private System.Single CalculateSignalStrength(System.Single distance, System.Single range);
```

- `private CalculateTelecomCoverage(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData) : System.Void`  

```csharp
private System.Void CalculateTelecomCoverage(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData);
```

- `private CalculateTelecomQuality(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData) : System.Single`  

```csharp
private System.Single CalculateTelecomQuality(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData);
```

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```

- `private GetEfficiencyFactor(Unity.Collections.NativeArray<Game.Buildings.TelecomFacility> telecomFacilities, Unity.Collections.NativeArray<Game.Tools.Temp> temps, Unity.Entities.BufferAccessor<Game.Buildings.Efficiency> efficiencyAccessor, System.Int32 i) : System.Single`  

```csharp
private System.Single GetEfficiencyFactor(Unity.Collections.NativeArray<Game.Buildings.TelecomFacility> telecomFacilities, Unity.Collections.NativeArray<Game.Tools.Temp> temps, Unity.Entities.BufferAccessor<Game.Buildings.Efficiency> efficiencyAccessor, System.Int32 i);
```

- `private ResetObstructAngles(Unity.Collections.NativeArray<System.Single> obstructAngles, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max) : System.Void`  

```csharp
private System.Void ResetObstructAngles(Unity.Collections.NativeArray<System.Single> obstructAngles, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max);
```


