# Game.UI.InGame.TaxationUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TaxationUISystem : Game.UI.UISystemBase
{
    private Game.Simulation.ITaxSystem m_TaxSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_ResourceQuery;
    private Unity.Entities.EntityQuery m_UnlockedZoneQuery;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxRate;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxIncome;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxEffect;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MinTaxRate;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MaxTaxRate;
    private Colossal.UI.Binding.RawValueBinding m_AreaTypes;
    private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxRates;
    private Colossal.UI.Binding.GetterMapBinding<System.Int32, Colossal.Mathematics.Bounds1> m_AreaResourceTaxRanges;
    private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxIncomes;
    private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxEffects;
    private Colossal.UI.Binding.GetterMapBinding<Game.UI.InGame.TaxResource, System.Int32> m_ResourceTaxRates;
    private Colossal.UI.Binding.GetterMapBinding<Game.UI.InGame.TaxResource, System.Int32> m_ResourceTaxIncomes;
    private Game.Prefabs.TaxParameterData m_CachedTaxParameterData;
    private System.Int32 m_CachedLockedOrderVersion;
    private System.Collections.Generic.Dictionary<System.Int32, System.String> m_ResourceIcons;
    private Game.UI.InGame.TaxationUISystem+TypeHandle __TypeHandle;
    private static readonly System.String kGroup;

    public TaxationUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Int32 GetEstimatedResourceTaxIncome(Game.Simulation.TaxAreaType type, System.Int32 resource);
    private System.String GetIcon(Game.Simulation.TaxAreaType type);
    private Unity.Mathematics.int2 GetLimits(Game.Simulation.TaxAreaType type, Game.Prefabs.TaxParameterData limits);
    private Unity.Mathematics.int2 GetResourceLimits(Game.Simulation.TaxAreaType type, Game.Prefabs.TaxParameterData limits);
    private System.Collections.Generic.IEnumerable<Game.Prefabs.ResourcePrefab> GetResources(System.Int32 areaType);
    private System.Int32 GetResourceTaxRate(Game.Simulation.TaxAreaType type, System.Int32 resource);
    private System.Boolean Locked(Game.Simulation.TaxAreaType areaType);
    private System.Boolean MatchArea(Game.Prefabs.TaxableResource data, System.Int32 areaType);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void SetAreaTaxRate(System.Int32 areaType, System.Int32 rate);
    private System.Void SetResourceTaxRate(System.Int32 resource, System.Int32 areaType, System.Int32 rate);
    private System.Void SetTaxRate(System.Int32 rate);
    private System.Void UpdateAreaResources(Colossal.UI.Binding.IJsonWriter binder, System.Int32 area);
    private Colossal.Mathematics.Bounds1 UpdateAreaResourceTaxRange(System.Int32 area);
    private System.Int32 UpdateAreaTaxEffect(System.Int32 areaType);
    private System.Int32 UpdateAreaTaxIncome(System.Int32 areaType);
    private System.Int32 UpdateAreaTaxRate(System.Int32 areaType);
    private System.Void UpdateAreaTypes(Colossal.UI.Binding.IJsonWriter binder);
    private System.Int32 UpdateMaxTaxRate();
    private System.Int32 UpdateMinTaxRate();
    private Game.UI.InGame.TaxResourceInfo UpdateResourceInfo(Game.UI.InGame.TaxResource resource);
    private System.Int32 UpdateResourceTaxIncome(Game.UI.InGame.TaxResource taxResource);
    private System.Int32 UpdateResourceTaxRate(Game.UI.InGame.TaxResource taxResource);
    private System.Int32 UpdateTaxEffect();
    private System.Int32 UpdateTaxIncome();
    private System.Int32 UpdateTaxRate();
}
```


## Fields

- `private Game.Simulation.ITaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.ITaxSystem m_TaxSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_ResourceQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResourceQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockedZoneQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedZoneQuery;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxRate`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxRate;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxIncome`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxIncome;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxEffect`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxEffect;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MinTaxRate`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MinTaxRate;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MaxTaxRate`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MaxTaxRate;
```

- `private Colossal.UI.Binding.RawValueBinding m_AreaTypes`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_AreaTypes;
```

- `private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxRates`  

```csharp
private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxRates;
```

- `private Colossal.UI.Binding.GetterMapBinding<System.Int32, Colossal.Mathematics.Bounds1> m_AreaResourceTaxRanges`  

```csharp
private Colossal.UI.Binding.GetterMapBinding<System.Int32, Colossal.Mathematics.Bounds1> m_AreaResourceTaxRanges;
```

- `private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxIncomes`  

```csharp
private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxIncomes;
```

- `private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxEffects`  

```csharp
private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxEffects;
```

- `private Colossal.UI.Binding.GetterMapBinding<Game.UI.InGame.TaxResource, System.Int32> m_ResourceTaxRates`  

```csharp
private Colossal.UI.Binding.GetterMapBinding<Game.UI.InGame.TaxResource, System.Int32> m_ResourceTaxRates;
```

- `private Colossal.UI.Binding.GetterMapBinding<Game.UI.InGame.TaxResource, System.Int32> m_ResourceTaxIncomes`  

```csharp
private Colossal.UI.Binding.GetterMapBinding<Game.UI.InGame.TaxResource, System.Int32> m_ResourceTaxIncomes;
```

- `private Game.Prefabs.TaxParameterData m_CachedTaxParameterData`  

```csharp
private Game.Prefabs.TaxParameterData m_CachedTaxParameterData;
```

- `private System.Int32 m_CachedLockedOrderVersion`  

```csharp
private System.Int32 m_CachedLockedOrderVersion;
```

- `private System.Collections.Generic.Dictionary<System.Int32, System.String> m_ResourceIcons`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, System.String> m_ResourceIcons;
```

- `private Game.UI.InGame.TaxationUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.TaxationUISystem+TypeHandle __TypeHandle;
```

- `private static readonly System.String kGroup`  

```csharp
private static readonly System.String kGroup;
```


## Constructors

- `public TaxationUISystem()`  

```csharp
public TaxationUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetEstimatedResourceTaxIncome(Game.Simulation.TaxAreaType type, System.Int32 resource) : System.Int32`  

```csharp
private System.Int32 GetEstimatedResourceTaxIncome(Game.Simulation.TaxAreaType type, System.Int32 resource);
```

- `private GetIcon(Game.Simulation.TaxAreaType type) : System.String`  

```csharp
private System.String GetIcon(Game.Simulation.TaxAreaType type);
```

- `private GetLimits(Game.Simulation.TaxAreaType type, Game.Prefabs.TaxParameterData limits) : Unity.Mathematics.int2`  

```csharp
private Unity.Mathematics.int2 GetLimits(Game.Simulation.TaxAreaType type, Game.Prefabs.TaxParameterData limits);
```

- `private GetResourceLimits(Game.Simulation.TaxAreaType type, Game.Prefabs.TaxParameterData limits) : Unity.Mathematics.int2`  

```csharp
private Unity.Mathematics.int2 GetResourceLimits(Game.Simulation.TaxAreaType type, Game.Prefabs.TaxParameterData limits);
```

- `private GetResources(System.Int32 areaType) : System.Collections.Generic.IEnumerable<Game.Prefabs.ResourcePrefab>`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Prefabs.ResourcePrefab> GetResources(System.Int32 areaType);
```

- `private GetResourceTaxRate(Game.Simulation.TaxAreaType type, System.Int32 resource) : System.Int32`  

```csharp
private System.Int32 GetResourceTaxRate(Game.Simulation.TaxAreaType type, System.Int32 resource);
```

- `private Locked(Game.Simulation.TaxAreaType areaType) : System.Boolean`  

```csharp
private System.Boolean Locked(Game.Simulation.TaxAreaType areaType);
```

- `private MatchArea(Game.Prefabs.TaxableResource data, System.Int32 areaType) : System.Boolean`  

```csharp
private System.Boolean MatchArea(Game.Prefabs.TaxableResource data, System.Int32 areaType);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private SetAreaTaxRate(System.Int32 areaType, System.Int32 rate) : System.Void`  

```csharp
private System.Void SetAreaTaxRate(System.Int32 areaType, System.Int32 rate);
```

- `private SetResourceTaxRate(System.Int32 resource, System.Int32 areaType, System.Int32 rate) : System.Void`  

```csharp
private System.Void SetResourceTaxRate(System.Int32 resource, System.Int32 areaType, System.Int32 rate);
```

- `private SetTaxRate(System.Int32 rate) : System.Void`  

```csharp
private System.Void SetTaxRate(System.Int32 rate);
```

- `private UpdateAreaResources(Colossal.UI.Binding.IJsonWriter binder, System.Int32 area) : System.Void`  

```csharp
private System.Void UpdateAreaResources(Colossal.UI.Binding.IJsonWriter binder, System.Int32 area);
```

- `private UpdateAreaResourceTaxRange(System.Int32 area) : Colossal.Mathematics.Bounds1`  

```csharp
private Colossal.Mathematics.Bounds1 UpdateAreaResourceTaxRange(System.Int32 area);
```

- `private UpdateAreaTaxEffect(System.Int32 areaType) : System.Int32`  

```csharp
private System.Int32 UpdateAreaTaxEffect(System.Int32 areaType);
```

- `private UpdateAreaTaxIncome(System.Int32 areaType) : System.Int32`  

```csharp
private System.Int32 UpdateAreaTaxIncome(System.Int32 areaType);
```

- `private UpdateAreaTaxRate(System.Int32 areaType) : System.Int32`  

```csharp
private System.Int32 UpdateAreaTaxRate(System.Int32 areaType);
```

- `private UpdateAreaTypes(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void UpdateAreaTypes(Colossal.UI.Binding.IJsonWriter binder);
```

- `private UpdateMaxTaxRate() : System.Int32`  

```csharp
private System.Int32 UpdateMaxTaxRate();
```

- `private UpdateMinTaxRate() : System.Int32`  

```csharp
private System.Int32 UpdateMinTaxRate();
```

- `private UpdateResourceInfo(Game.UI.InGame.TaxResource resource) : Game.UI.InGame.TaxResourceInfo`  

```csharp
private Game.UI.InGame.TaxResourceInfo UpdateResourceInfo(Game.UI.InGame.TaxResource resource);
```

- `private UpdateResourceTaxIncome(Game.UI.InGame.TaxResource taxResource) : System.Int32`  

```csharp
private System.Int32 UpdateResourceTaxIncome(Game.UI.InGame.TaxResource taxResource);
```

- `private UpdateResourceTaxRate(Game.UI.InGame.TaxResource taxResource) : System.Int32`  

```csharp
private System.Int32 UpdateResourceTaxRate(Game.UI.InGame.TaxResource taxResource);
```

- `private UpdateTaxEffect() : System.Int32`  

```csharp
private System.Int32 UpdateTaxEffect();
```

- `private UpdateTaxIncome() : System.Int32`  

```csharp
private System.Int32 UpdateTaxIncome();
```

- `private UpdateTaxRate() : System.Int32`  

```csharp
private System.Int32 UpdateTaxRate();
```


## Nested types

- `Game.UI.InGame.TaxationUISystem+TypeHandle`  
- `Game.UI.InGame.TaxationUISystem+<GetResources>d__46`  

