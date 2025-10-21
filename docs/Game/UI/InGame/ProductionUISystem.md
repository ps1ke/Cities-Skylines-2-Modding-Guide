# Game.UI.InGame.ProductionUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ProductionUISystem : Game.UI.UISystemBase
{
    private Game.UI.UIUpdateState m_UpdateState;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
    private Unity.Entities.EntityQuery m_ResourceCategoryQuery;
    private Unity.Entities.EntityQuery m_IndustrialCompanyQuery;
    private Unity.Entities.EntityQuery m_CommercialCompanyQuery;
    private Unity.Entities.EntityQuery m_ServiceUpkeepQuery;
    private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> m_ProductionChain;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MaxProgressBinding;
    private Colossal.UI.Binding.RawValueBinding m_ResourceCategoriesBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ResourceDetailsBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ResourceBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ServiceBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_DataBinding;
    private Unity.Collections.NativeList<System.Int32> m_ProductionCache;
    private Unity.Collections.NativeList<System.Int32> m_CommercialConsumptionCache;
    private Unity.Collections.NativeList<System.Int32> m_IndustrialConsumptionCache;
    private static const System.String kGroup;

    public ProductionUISystem();

    private System.Void BuildProductionChain(Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap);
    private System.Void FindOutputs(Unity.Entities.Entity entity, Unity.Collections.NativeList<Unity.Entities.Entity> outputs, Unity.Collections.NativeKeyValueArrays<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> keyValueArrays);
    private System.Void FindServiceOutputs(Unity.Entities.Entity entity, Unity.Collections.NativeList<Unity.Entities.Entity> outputs, Unity.Collections.NativeArray<Unity.Entities.Entity> serviceUpkeeps);
    private System.ValueTuple<System.Int32, System.Int32, System.Int32> GetData(Unity.Entities.Entity entity);
    private System.Int32 GetMaxProgress();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void ProcessProductionChainDatas(Unity.Collections.NativeArray<Game.Prefabs.IndustrialProcessData> datas, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap);
    private static System.Void TryAddUniqueValue(Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap, Unity.Entities.Entity key, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity> value);
    private System.Void UpdateCache();
    private System.Void WriteData(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
    private System.Void WriteProductionLink(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UIProductionLinkPrefab prefab);
    public System.Void WriteResource(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
    private System.Void WriteResourceCategories(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteResourceDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
    private System.Void WriteService(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
}
```


## Fields

- `private Game.UI.UIUpdateState m_UpdateState`  

```csharp
private Game.UI.UIUpdateState m_UpdateState;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem`  

```csharp
private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  

```csharp
private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
```

- `private Unity.Entities.EntityQuery m_ResourceCategoryQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResourceCategoryQuery;
```

- `private Unity.Entities.EntityQuery m_IndustrialCompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_IndustrialCompanyQuery;
```

- `private Unity.Entities.EntityQuery m_CommercialCompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_CommercialCompanyQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceUpkeepQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceUpkeepQuery;
```

- `private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> m_ProductionChain`  

```csharp
private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> m_ProductionChain;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MaxProgressBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MaxProgressBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_ResourceCategoriesBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ResourceCategoriesBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ResourceDetailsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ResourceDetailsBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ResourceBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ResourceBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ServiceBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ServiceBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_DataBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_DataBinding;
```

- `private Unity.Collections.NativeList<System.Int32> m_ProductionCache`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_ProductionCache;
```

- `private Unity.Collections.NativeList<System.Int32> m_CommercialConsumptionCache`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_CommercialConsumptionCache;
```

- `private Unity.Collections.NativeList<System.Int32> m_IndustrialConsumptionCache`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_IndustrialConsumptionCache;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public ProductionUISystem()`  

```csharp
public ProductionUISystem();
```


## Methods

- `private BuildProductionChain(Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap) : System.Void`  

```csharp
private System.Void BuildProductionChain(Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap);
```

- `private FindOutputs(Unity.Entities.Entity entity, Unity.Collections.NativeList<Unity.Entities.Entity> outputs, Unity.Collections.NativeKeyValueArrays<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> keyValueArrays) : System.Void`  

```csharp
private System.Void FindOutputs(Unity.Entities.Entity entity, Unity.Collections.NativeList<Unity.Entities.Entity> outputs, Unity.Collections.NativeKeyValueArrays<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> keyValueArrays);
```

- `private FindServiceOutputs(Unity.Entities.Entity entity, Unity.Collections.NativeList<Unity.Entities.Entity> outputs, Unity.Collections.NativeArray<Unity.Entities.Entity> serviceUpkeeps) : System.Void`  

```csharp
private System.Void FindServiceOutputs(Unity.Entities.Entity entity, Unity.Collections.NativeList<Unity.Entities.Entity> outputs, Unity.Collections.NativeArray<Unity.Entities.Entity> serviceUpkeeps);
```

- `private GetData(Unity.Entities.Entity entity) : System.ValueTuple<System.Int32, System.Int32, System.Int32>`  

```csharp
private System.ValueTuple<System.Int32, System.Int32, System.Int32> GetData(Unity.Entities.Entity entity);
```

- `private GetMaxProgress() : System.Int32`  

```csharp
private System.Int32 GetMaxProgress();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private ProcessProductionChainDatas(Unity.Collections.NativeArray<Game.Prefabs.IndustrialProcessData> datas, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap) : System.Void`  

```csharp
private System.Void ProcessProductionChainDatas(Unity.Collections.NativeArray<Game.Prefabs.IndustrialProcessData> datas, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap);
```

- `private static TryAddUniqueValue(Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap, Unity.Entities.Entity key, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity> value) : System.Void`  

```csharp
private static System.Void TryAddUniqueValue(Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap, Unity.Entities.Entity key, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity> value);
```

- `private UpdateCache() : System.Void`  

```csharp
private System.Void UpdateCache();
```

- `private WriteData(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void WriteData(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
```

- `private WriteProductionLink(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UIProductionLinkPrefab prefab) : System.Void`  

```csharp
private System.Void WriteProductionLink(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UIProductionLinkPrefab prefab);
```

- `public WriteResource(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void WriteResource(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
```

- `private WriteResourceCategories(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void WriteResourceCategories(Colossal.UI.Binding.IJsonWriter writer);
```

- `private WriteResourceDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void WriteResourceDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
```

- `private WriteService(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void WriteService(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
```


