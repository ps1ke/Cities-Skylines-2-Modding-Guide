# Game.Buildings.PropertyUtils+CompanyFindPropertyJob

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct CompanyFindPropertyJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.ComponentTypeHandle<Game.Companies.CompanyData> m_CompanyDataType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabType;
    public Unity.Entities.ComponentTypeHandle<Game.Agents.PropertySeeker> m_PropertySeekerType;
    public Unity.Entities.ComponentTypeHandle<Game.Companies.StorageCompany> m_StorageCompanyType;
    public Unity.Collections.NativeList<Unity.Entities.Entity> m_FreePropertyEntities;
    public Unity.Collections.NativeList<Game.Prefabs.PrefabRef> m_PropertyPrefabs;
    public Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_IndustrialProcessDatas;
    public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_BuildingPropertyDatas;
    public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters;
    public Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> m_Availabilities;
    public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Buildings;
    public Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> m_PropertiesOnMarket;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabFromEntity;
    public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingDatas;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas;
    public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableDatas;
    public Unity.Entities.ComponentLookup<Game.Prefabs.WorkplaceData> m_WorkplaceDatas;
    public Unity.Entities.ComponentLookup<Game.Net.LandValue> m_LandValues;
    public Unity.Entities.ComponentLookup<Game.Companies.ServiceCompanyData> m_ServiceCompanies;
    public Unity.Entities.ComponentLookup<Game.Companies.CommercialCompany> m_CommercialCompanies;
    public Unity.Entities.ComponentLookup<Game.Buildings.Signature> m_Signatures;
    public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_Renters;
    public Game.Prefabs.ResourcePrefabs m_ResourcePrefabs;
    public Game.Prefabs.EconomyParameterData m_EconomyParameters;
    public Game.Prefabs.ZonePreferenceData m_ZonePreferences;
    public System.Boolean m_Commercial;
    public Unity.Collections.NativeQueue<Game.Buildings.RentAction> m_RentActionQueue;
    public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;

    private System.Void Evaluate(System.Int32 index, Unity.Entities.Entity company, Game.Companies.ServiceCompanyData& service, Game.Prefabs.IndustrialProcessData& process, Unity.Entities.Entity property, Game.Agents.PropertySeeker& propertySeeker, System.Boolean commercial, System.Boolean storage);
    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Boolean PropertyAllowsResource(System.Int32 index, Game.Economy.Resource resource, Game.Economy.Resource input, System.Boolean storage);
    private System.Void SelectProperty(System.Int32 jobIndex, Unity.Entities.Entity company, Game.Agents.PropertySeeker& propertySeeker, System.Boolean storage);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Companies.CompanyData> m_CompanyDataType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Companies.CompanyData> m_CompanyDataType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Agents.PropertySeeker> m_PropertySeekerType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Agents.PropertySeeker> m_PropertySeekerType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Companies.StorageCompany> m_StorageCompanyType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Companies.StorageCompany> m_StorageCompanyType;
```

- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_FreePropertyEntities`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.Entity> m_FreePropertyEntities;
```

- `public Unity.Collections.NativeList<Game.Prefabs.PrefabRef> m_PropertyPrefabs`  

```csharp
public Unity.Collections.NativeList<Game.Prefabs.PrefabRef> m_PropertyPrefabs;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_IndustrialProcessDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_IndustrialProcessDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_BuildingPropertyDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_BuildingPropertyDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters;
```

- `public Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> m_Availabilities`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> m_Availabilities;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Buildings`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Buildings;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> m_PropertiesOnMarket`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> m_PropertiesOnMarket;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabFromEntity`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabFromEntity;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.WorkplaceData> m_WorkplaceDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.WorkplaceData> m_WorkplaceDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Net.LandValue> m_LandValues`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.LandValue> m_LandValues;
```

- `public Unity.Entities.ComponentLookup<Game.Companies.ServiceCompanyData> m_ServiceCompanies`  

```csharp
public Unity.Entities.ComponentLookup<Game.Companies.ServiceCompanyData> m_ServiceCompanies;
```

- `public Unity.Entities.ComponentLookup<Game.Companies.CommercialCompany> m_CommercialCompanies`  

```csharp
public Unity.Entities.ComponentLookup<Game.Companies.CommercialCompany> m_CommercialCompanies;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Signature> m_Signatures`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Signature> m_Signatures;
```

- `public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_Renters`  

```csharp
public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_Renters;
```

- `public Game.Prefabs.ResourcePrefabs m_ResourcePrefabs`  

```csharp
public Game.Prefabs.ResourcePrefabs m_ResourcePrefabs;
```

- `public Game.Prefabs.EconomyParameterData m_EconomyParameters`  

```csharp
public Game.Prefabs.EconomyParameterData m_EconomyParameters;
```

- `public Game.Prefabs.ZonePreferenceData m_ZonePreferences`  

```csharp
public Game.Prefabs.ZonePreferenceData m_ZonePreferences;
```

- `public System.Boolean m_Commercial`  

```csharp
public System.Boolean m_Commercial;
```

- `public Unity.Collections.NativeQueue<Game.Buildings.RentAction> m_RentActionQueue`  

```csharp
public Unity.Collections.NativeQueue<Game.Buildings.RentAction> m_RentActionQueue;
```

- `public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer`  

```csharp
public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;
```


## Methods

- `private Evaluate(System.Int32 index, Unity.Entities.Entity company, Game.Companies.ServiceCompanyData& service, Game.Prefabs.IndustrialProcessData& process, Unity.Entities.Entity property, Game.Agents.PropertySeeker& propertySeeker, System.Boolean commercial, System.Boolean storage) : System.Void`  

```csharp
private System.Void Evaluate(System.Int32 index, Unity.Entities.Entity company, Game.Companies.ServiceCompanyData& service, Game.Prefabs.IndustrialProcessData& process, Unity.Entities.Entity property, Game.Agents.PropertySeeker& propertySeeker, System.Boolean commercial, System.Boolean storage);
```

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```

- `private PropertyAllowsResource(System.Int32 index, Game.Economy.Resource resource, Game.Economy.Resource input, System.Boolean storage) : System.Boolean`  

```csharp
private System.Boolean PropertyAllowsResource(System.Int32 index, Game.Economy.Resource resource, Game.Economy.Resource input, System.Boolean storage);
```

- `private SelectProperty(System.Int32 jobIndex, Unity.Entities.Entity company, Game.Agents.PropertySeeker& propertySeeker, System.Boolean storage) : System.Void`  

```csharp
private System.Void SelectProperty(System.Int32 jobIndex, Unity.Entities.Entity company, Game.Agents.PropertySeeker& propertySeeker, System.Boolean storage);
```

- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```


