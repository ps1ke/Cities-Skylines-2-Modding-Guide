# Game.Simulation.TelecomCoverageSystem+TelecomCoverageJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_DensityChunks`  
- `public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_FacilityChunks`  
- `public Game.Simulation.TerrainHeightData m_TerrainHeightData`  
- `public Unity.Entities.Entity m_City`  
- `public System.Boolean m_Preview`  
- `public Unity.Collections.NativeArray<Game.Simulation.TelecomCoverage> m_TelecomCoverage`  
- `public Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_TelecomStatus`  
- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_TransformType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.PropertyRenter> m_PropertyRenterType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.TelecomFacility> m_TelecomFacilityType`  
- `public Unity.Entities.BufferTypeHandle<Game.Buildings.Efficiency> m_BuildingEfficiencyType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_TempType`  
- `public Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType`  
- `public Unity.Entities.BufferTypeHandle<Game.Citizens.HouseholdCitizen> m_HouseholdCitizenType`  
- `public Unity.Entities.BufferTypeHandle<Game.Companies.Employee> m_EmployeeType`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.TelecomFacility> m_TelecomFacilityData`  
- `public Unity.Entities.BufferLookup<Game.Buildings.Efficiency> m_BuildingEfficiencyData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_ObjectGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.TelecomFacilityData> m_PrefabTelecomFacilityData`  
- `public Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers`  

## Methods

- `private AddDensity(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, Unity.Entities.ArchetypeChunk chunk) : System.Void`  
- `private AddDensity(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, System.Int32 density, Unity.Mathematics.float3 position) : System.Void`  
- `private AddNetworkCapacity(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeList<System.Single> signalStrengths, Unity.Entities.ArchetypeChunk chunk, System.Int32& arrayIndex, Game.Simulation.TelecomStatus& status, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers) : System.Void`  
- `private AddNetworkCapacity(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, System.Single capacity) : System.Void`  
- `private AddSignalStrengths(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max) : System.Void`  
- `private CalculateCellSignalStrength(Unity.Collections.NativeArray<System.Single> obstructSlopes, Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 cell, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, System.Single range, Unity.Mathematics.float3 position) : System.Void`  
- `private CalculateNetworkUsers(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max) : System.Single`  
- `private CalculateSignalStrength(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData, Unity.Collections.NativeArray<System.Single> obstructSlopes, Unity.Collections.NativeList<System.Single> signalStrengths, Unity.Entities.ArchetypeChunk chunk, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers) : System.Void`  
- `private CalculateSignalStrength(Unity.Collections.NativeArray<System.Single> signalStrengthArray, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, System.Single range, Unity.Mathematics.float3 position) : System.Void`  
- `private CalculateSignalStrength(System.Single distance, System.Single range) : System.Single`  
- `private CalculateTelecomCoverage(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData) : System.Void`  
- `private CalculateTelecomQuality(Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellDensityData> densityData, Unity.Collections.NativeArray<Game.Simulation.TelecomCoverageSystem+CellFacilityData> facilityData) : System.Single`  
- `public Execute() : System.Void`  
- `private GetEfficiencyFactor(Unity.Collections.NativeArray<Game.Buildings.TelecomFacility> telecomFacilities, Unity.Collections.NativeArray<Game.Tools.Temp> temps, Unity.Entities.BufferAccessor<Game.Buildings.Efficiency> efficiencyAccessor, System.Int32 i) : System.Single`  
- `private ResetObstructAngles(Unity.Collections.NativeArray<System.Single> obstructAngles, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max) : System.Void`  

