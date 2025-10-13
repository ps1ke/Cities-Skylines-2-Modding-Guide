# Game.Buildings.PropertyUtils+ExtractorFindCompanyJob

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct ExtractorFindCompanyJob : Unity.Jobs.IJob
{
    public Unity.Collections.NativeList<Unity.Entities.Entity> m_Entities;
    public Unity.Collections.NativeList<Unity.Entities.Entity> m_ExtractorCompanyEntities;
    public Unity.Collections.NativeList<Unity.Entities.Entity> m_CompanyPrefabs;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs;
    public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_Properties;
    public Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_Processes;
    public Unity.Entities.ComponentLookup<Game.Prefabs.WorkplaceData> m_WorkplaceDatas;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas;
    public Unity.Entities.ComponentLookup<Game.Objects.Attached> m_Attached;
    public Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas;
    public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades;
    public Unity.Entities.ComponentLookup<Game.Areas.Lot> m_Lots;
    public Unity.Entities.ComponentLookup<Game.Areas.Geometry> m_Geometries;
    public Unity.Entities.ComponentLookup<Game.Areas.Extractor> m_ExtractorAreas;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> m_ExtractorDatas;
    public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters;
    public Game.Prefabs.ResourcePrefabs m_ResourcePrefabs;
    public Game.Prefabs.ExtractorParameterData m_ExtractorParameters;
    public Game.Prefabs.EconomyParameterData m_EconomyParameters;
    public Unity.Collections.NativeQueue<Game.Buildings.RentAction> m_RentActionQueue;
    public Unity.Entities.EntityCommandBuffer m_CommandBuffer;
    public System.Single m_AverageTemperature;
    public Unity.Collections.NativeArray<System.Int32> m_Productions;
    public Unity.Collections.NativeArray<System.Int32> m_Consumptions;

    private System.Single Evaluate(Unity.Entities.Entity entity, Game.Economy.Resource resource);
    public System.Void Execute();
}
```


## Fields

- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_Entities`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.Entity> m_Entities;
```

- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_ExtractorCompanyEntities`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.Entity> m_ExtractorCompanyEntities;
```

- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_CompanyPrefabs`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.Entity> m_CompanyPrefabs;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_Properties`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_Properties;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_Processes`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_Processes;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.WorkplaceData> m_WorkplaceDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.WorkplaceData> m_WorkplaceDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Attached> m_Attached`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Attached> m_Attached;
```

- `public Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas;
```

- `public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades`  

```csharp
public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades;
```

- `public Unity.Entities.ComponentLookup<Game.Areas.Lot> m_Lots`  

```csharp
public Unity.Entities.ComponentLookup<Game.Areas.Lot> m_Lots;
```

- `public Unity.Entities.ComponentLookup<Game.Areas.Geometry> m_Geometries`  

```csharp
public Unity.Entities.ComponentLookup<Game.Areas.Geometry> m_Geometries;
```

- `public Unity.Entities.ComponentLookup<Game.Areas.Extractor> m_ExtractorAreas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Areas.Extractor> m_ExtractorAreas;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> m_ExtractorDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> m_ExtractorDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters;
```

- `public Game.Prefabs.ResourcePrefabs m_ResourcePrefabs`  

```csharp
public Game.Prefabs.ResourcePrefabs m_ResourcePrefabs;
```

- `public Game.Prefabs.ExtractorParameterData m_ExtractorParameters`  

```csharp
public Game.Prefabs.ExtractorParameterData m_ExtractorParameters;
```

- `public Game.Prefabs.EconomyParameterData m_EconomyParameters`  

```csharp
public Game.Prefabs.EconomyParameterData m_EconomyParameters;
```

- `public Unity.Collections.NativeQueue<Game.Buildings.RentAction> m_RentActionQueue`  

```csharp
public Unity.Collections.NativeQueue<Game.Buildings.RentAction> m_RentActionQueue;
```

- `public Unity.Entities.EntityCommandBuffer m_CommandBuffer`  

```csharp
public Unity.Entities.EntityCommandBuffer m_CommandBuffer;
```

- `public System.Single m_AverageTemperature`  

```csharp
public System.Single m_AverageTemperature;
```

- `public Unity.Collections.NativeArray<System.Int32> m_Productions`  

```csharp
public Unity.Collections.NativeArray<System.Int32> m_Productions;
```

- `public Unity.Collections.NativeArray<System.Int32> m_Consumptions`  

```csharp
public Unity.Collections.NativeArray<System.Int32> m_Consumptions;
```


## Methods

- `private Evaluate(Unity.Entities.Entity entity, Game.Economy.Resource resource) : System.Single`  

```csharp
private System.Single Evaluate(Unity.Entities.Entity entity, Game.Economy.Resource resource);
```

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```


