# Game.UI.InGame.PoliciesUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `public System.Action EventPolicyUnlocked`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  
- `private Game.UI.InGame.SelectedInfoUISystem m_InfoSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.UI.ImageSystem m_ImageSystem`  
- `private Unity.Entities.EntityQuery m_CityPoliciesQuery`  
- `private Unity.Entities.EntityQuery m_CityPoliciesUpdatedQuery`  
- `private Unity.Entities.EntityQuery m_DistrictPoliciesQuery`  
- `private Unity.Entities.EntityQuery m_BuildingPoliciesQuery`  
- `private Unity.Entities.EntityQuery m_RoutePoliciesQuery`  
- `private Unity.Entities.EntityQuery m_PolicyUnlockedQuery`  
- `private Unity.Entities.EntityArchetype m_PolicyEventArchetype`  
- `private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> m_CityPolicies`  
- `private System.Collections.Generic.List<Game.UI.InGame.UIPolicy> m_SelectedInfoPolicies`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.UI.InGame.UIPolicy>> m_CityPoliciesBinding`  
- `private Game.UI.InGame.PoliciesUISystem+TypeHandle __TypeHandle`  
- `public static const System.String kGroup`  

## Constructors

- `public PoliciesUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public BindBuildingPolicies(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private BindCityPolicies() : System.Collections.Generic.List<Game.UI.InGame.UIPolicy>`  
- `public BindDistrictPolicies(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private BindPolicies(Colossal.UI.Binding.IJsonWriter binder, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> list) : System.Void`  
- `public BindRoutePolicies(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private ExtractInfo(Unity.Entities.Entity entity, Game.Prefabs.PolicyPrefab prefab, Unity.Entities.DynamicBuffer<Game.Policies.Policy> activePolicies, System.Boolean slider, Game.Prefabs.PolicySliderData sliderData, System.Int32 priority) : Game.UI.InGame.UIPolicy`  
- `private FilterPolicy(Unity.Entities.Entity policy, Game.Prefabs.PolicyPrefab prefab, Unity.Entities.Entity target) : System.Boolean`  
- `private FindAndSortPolicies(Unity.Entities.Entity entity, Unity.Entities.EntityQuery policyQuery, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> list) : System.Void`  
- `public GatherSelectedInfoPolicies(Unity.Entities.Entity target) : System.Boolean`  
- `private HasParkingLanes(Unity.Entities.Entity building) : System.Boolean`  
- `private HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Objects.SubObject> subObjects) : System.Boolean`  
- `private HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets) : System.Boolean`  
- `private HasParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubLane> subLanes) : System.Boolean`  
- `private ModifyPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private RefreshCityPolicyAchievement(Unity.Entities.Entity policy, System.Boolean active) : System.Void`  
- `public SetCityPolicy(Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment) : System.Void`  
- `public SetPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment = 0) : System.Void`  
- `public SetSelectedInfoPolicy(Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment = 0) : System.Void`  
- `public SetSelectedInfoPolicy(Unity.Entities.Entity target, Unity.Entities.Entity policy, System.Boolean active, System.Single adjustment = 0) : System.Void`  
- `private WriteCityPolicies(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.List<Game.UI.InGame.UIPolicy> policies) : System.Void`  

## Nested types

- `Game.UI.InGame.PoliciesUISystem+BindingNames`  
- `Game.UI.InGame.PoliciesUISystem+TypeHandle`  

