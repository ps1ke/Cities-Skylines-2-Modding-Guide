# Game.UI.InGame.ProductionUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.UIUpdateState m_UpdateState`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem`  
- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  
- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  
- `private Unity.Entities.EntityQuery m_ResourceCategoryQuery`  
- `private Unity.Entities.EntityQuery m_IndustrialCompanyQuery`  
- `private Unity.Entities.EntityQuery m_CommercialCompanyQuery`  
- `private Unity.Entities.EntityQuery m_ServiceUpkeepQuery`  
- `private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> m_ProductionChain`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MaxProgressBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_ResourceCategoriesBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ResourceDetailsBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ResourceBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ServiceBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_DataBinding`  
- `private Unity.Collections.NativeList<System.Int32> m_ProductionCache`  
- `private Unity.Collections.NativeList<System.Int32> m_CommercialConsumptionCache`  
- `private Unity.Collections.NativeList<System.Int32> m_IndustrialConsumptionCache`  
- `private static const System.String kGroup`  

## Constructors

- `public ProductionUISystem()`  

## Methods

- `private BuildProductionChain(Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap) : System.Void`  
- `private FindOutputs(Unity.Entities.Entity entity, Unity.Collections.NativeList<Unity.Entities.Entity> outputs, Unity.Collections.NativeKeyValueArrays<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> keyValueArrays) : System.Void`  
- `private FindServiceOutputs(Unity.Entities.Entity entity, Unity.Collections.NativeList<Unity.Entities.Entity> outputs, Unity.Collections.NativeArray<Unity.Entities.Entity> serviceUpkeeps) : System.Void`  
- `private GetData(Unity.Entities.Entity entity) : System.ValueTuple<System.Int32, System.Int32, System.Int32>`  
- `private GetMaxProgress() : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private ProcessProductionChainDatas(Unity.Collections.NativeArray<Game.Prefabs.IndustrialProcessData> datas, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap) : System.Void`  
- `private static TryAddUniqueValue(Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap, Unity.Entities.Entity key, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity> value) : System.Void`  
- `private UpdateCache() : System.Void`  
- `private WriteData(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  
- `private WriteProductionLink(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UIProductionLinkPrefab prefab) : System.Void`  
- `public WriteResource(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  
- `private WriteResourceCategories(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private WriteResourceDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  
- `private WriteService(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

