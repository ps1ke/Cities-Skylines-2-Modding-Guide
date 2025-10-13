# Game.UI.InGame.PoliciesUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PoliciesUISystem : Game.UI.UISystemBase
{
    public System.Action EventPolicyUnlocked;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.UI.InGame.SelectedInfoUISystem m_InfoSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.UI.ImageSystem m_ImageSystem;
    private Unity.Entities.EntityQuery m_CityPoliciesQuery;
    private Unity.Entities.EntityQuery m_CityPoliciesUpdatedQuery;
    private Unity.Entities.EntityQuery m_DistrictPoliciesQuery;
    private Unity.Entities.EntityQuery m_BuildingPoliciesQuery;
    private Unity.Entities.EntityQuery m_RoutePoliciesQuery;
    private Unity.Entities.EntityQuery m_PolicyUnlockedQuery;
    private Unity.Entities.EntityArchetype m_PolicyEventArchetype;
    private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> m_CityPolicies;
    private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> m_SelectedInfoPolicies;
    private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.UI.InGame.UIPolicy>> m_CityPoliciesBinding;
    private Game.UI.InGame.PoliciesUISystem+TypeHandle __TypeHandle;
    public static const System.String kGroup;

    public PoliciesUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void BindBuildingPolicies(Colossal.UI.Binding.IJsonWriter binder);
    private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> BindCityPolicies();
    public System.Void BindDistrictPolicies(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void BindPolicies(Colossal.UI.Binding.IJsonWriter binder, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> list);
    public System.Void BindRoutePolicies(Colossal.UI.Binding.IJsonWriter binder);
    private Game.UI.InGame.UIPolicy ExtractInfo(Unity.Entities.Entity entity, Game.Prefabs.PolicyPrefab prefab, Unity.Entities.DynamicBuffer<Game.Policies.Policy> activePolicies, System.Boolean slider, Game.Prefabs.PolicySliderData sliderData, System.Int32 priority);
    private System.Boolean FilterPolicy(Unity.Entities.Entity policy, Game.Prefabs.PolicyPrefab prefab, Unity.Entities.Entity target);
    private System.Void FindAndSortPolicies(Unity.Entities.Entity entity, Unity.Entities.EntityQuery policyQuery, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> list);
    public System.Boolean GatherSelectedInfoPolicies(Unity.Entities.Entity target);
    private System.Boolean HasParkingLanes(Unity.Entities.Entity building);
    private System.Boolean HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Objects.SubObject> subObjects);
    private System.Boolean HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets);
    private System.Boolean HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubLane> subLanes);
    private System.Void ModifyPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void RefreshCityPolicyAchievement(Unity.Entities.Entity policy, System.Boolean active);
    public System.Void SetCityPolicy(Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment);
    public System.Void SetPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment);
    public System.Void SetSelectedInfoPolicy(Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment);
    public System.Void SetSelectedInfoPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment);
    private System.Void WriteCityPolicies(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> policies);
}
```


## Fields

- `public System.Action EventPolicyUnlocked`  

```csharp
public System.Action EventPolicyUnlocked;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.UI.InGame.SelectedInfoUISystem m_InfoSystem`  

```csharp
private Game.UI.InGame.SelectedInfoUISystem m_InfoSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Unity.Entities.EntityQuery m_CityPoliciesQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityPoliciesQuery;
```

- `private Unity.Entities.EntityQuery m_CityPoliciesUpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityPoliciesUpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_DistrictPoliciesQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictPoliciesQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingPoliciesQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingPoliciesQuery;
```

- `private Unity.Entities.EntityQuery m_RoutePoliciesQuery`  

```csharp
private Unity.Entities.EntityQuery m_RoutePoliciesQuery;
```

- `private Unity.Entities.EntityQuery m_PolicyUnlockedQuery`  

```csharp
private Unity.Entities.EntityQuery m_PolicyUnlockedQuery;
```

- `private Unity.Entities.EntityArchetype m_PolicyEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PolicyEventArchetype;
```

- `private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> m_CityPolicies`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> m_CityPolicies;
```

- `private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> m_SelectedInfoPolicies`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> m_SelectedInfoPolicies;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.UI.InGame.UIPolicy>> m_CityPoliciesBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.UI.InGame.UIPolicy>> m_CityPoliciesBinding;
```

- `private Game.UI.InGame.PoliciesUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.PoliciesUISystem+TypeHandle __TypeHandle;
```

- `public static const System.String kGroup`  

```csharp
public static const System.String kGroup;
```


## Constructors

- `public PoliciesUISystem()`  

```csharp
public PoliciesUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public BindBuildingPolicies(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
public System.Void BindBuildingPolicies(Colossal.UI.Binding.IJsonWriter binder);
```

- `private BindCityPolicies() : System.Collections.Generic.List<Game.UI.InGame.UIPolicy>`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> BindCityPolicies();
```

- `public BindDistrictPolicies(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
public System.Void BindDistrictPolicies(Colossal.UI.Binding.IJsonWriter binder);
```

- `private BindPolicies(Colossal.UI.Binding.IJsonWriter binder, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> list) : System.Void`  

```csharp
private System.Void BindPolicies(Colossal.UI.Binding.IJsonWriter binder, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> list);
```

- `public BindRoutePolicies(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
public System.Void BindRoutePolicies(Colossal.UI.Binding.IJsonWriter binder);
```

- `private ExtractInfo(Unity.Entities.Entity entity, Game.Prefabs.PolicyPrefab prefab, Unity.Entities.DynamicBuffer<Game.Policies.Policy> activePolicies, System.Boolean slider, Game.Prefabs.PolicySliderData sliderData, System.Int32 priority) : Game.UI.InGame.UIPolicy`  

```csharp
private Game.UI.InGame.UIPolicy ExtractInfo(Unity.Entities.Entity entity, Game.Prefabs.PolicyPrefab prefab, Unity.Entities.DynamicBuffer<Game.Policies.Policy> activePolicies, System.Boolean slider, Game.Prefabs.PolicySliderData sliderData, System.Int32 priority);
```

- `private FilterPolicy(Unity.Entities.Entity policy, Game.Prefabs.PolicyPrefab prefab, Unity.Entities.Entity target) : System.Boolean`  

```csharp
private System.Boolean FilterPolicy(Unity.Entities.Entity policy, Game.Prefabs.PolicyPrefab prefab, Unity.Entities.Entity target);
```

- `private FindAndSortPolicies(Unity.Entities.Entity entity, Unity.Entities.EntityQuery policyQuery, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> list) : System.Void`  

```csharp
private System.Void FindAndSortPolicies(Unity.Entities.Entity entity, Unity.Entities.EntityQuery policyQuery, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> list);
```

- `public GatherSelectedInfoPolicies(Unity.Entities.Entity target) : System.Boolean`  

```csharp
public System.Boolean GatherSelectedInfoPolicies(Unity.Entities.Entity target);
```

- `private HasParkingLanes(Unity.Entities.Entity building) : System.Boolean`  

```csharp
private System.Boolean HasParkingLanes(Unity.Entities.Entity building);
```

- `private HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Objects.SubObject> subObjects) : System.Boolean`  

```csharp
private System.Boolean HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Objects.SubObject> subObjects);
```

- `private HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets) : System.Boolean`  

```csharp
private System.Boolean HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets);
```

- `private HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubLane> subLanes) : System.Boolean`  

```csharp
private System.Boolean HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubLane> subLanes);
```

- `private ModifyPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment) : System.Void`  

```csharp
private System.Void ModifyPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
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

- `private RefreshCityPolicyAchievement(Unity.Entities.Entity policy, System.Boolean active) : System.Void`  

```csharp
private System.Void RefreshCityPolicyAchievement(Unity.Entities.Entity policy, System.Boolean active);
```

- `public SetCityPolicy(Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment) : System.Void`  

```csharp
public System.Void SetCityPolicy(Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment);
```

- `public SetPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment = 0) : System.Void`  

```csharp
public System.Void SetPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment);
```

- `public SetSelectedInfoPolicy(Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment = 0) : System.Void`  

```csharp
public System.Void SetSelectedInfoPolicy(Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment);
```

- `public SetSelectedInfoPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment = 0) : System.Void`  

```csharp
public System.Void SetSelectedInfoPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment);
```

- `private WriteCityPolicies(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> policies) : System.Void`  

```csharp
private System.Void WriteCityPolicies(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> policies);
```


## Nested types

- `Game.UI.InGame.PoliciesUISystem+BindingNames`  
- `Game.UI.InGame.PoliciesUISystem+TypeHandle`  

