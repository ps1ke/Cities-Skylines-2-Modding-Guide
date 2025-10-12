# Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> m_PolicySliderData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.RouteOptionData> m_RouteOptionData`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.RouteModifierData> m_RouteModifierData`  

## Constructors

- `public RouteModifierRefreshData(Unity.Entities.SystemBase system)`  

## Methods

- `private static AddModifier(Unity.Entities.DynamicBuffer<Game.Routes.RouteModifier> modifiers, Game.Prefabs.RouteModifierData modifierData, System.Single delta) : System.Void`  
- `public static AddModifierData(Game.Routes.RouteModifier& modifier, Game.Prefabs.RouteModifierData modifierData, System.Single delta) : System.Void`  
- `public static GetDeltaFromModifier(Game.Routes.RouteModifier modifier, Game.Prefabs.RouteModifierData modifierData) : System.Single`  
- `public static GetModifierDelta(Game.Prefabs.RouteModifierData modifierData, System.Single policyAdjustment, Unity.Entities.Entity policy, Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> policySliderData) : System.Single`  
- `public static GetPolicyAdjustmentFromModifierDelta(Game.Prefabs.RouteModifierData modifierData, System.Single modifierDelta, Game.Prefabs.PolicySliderData sliderData) : System.Single`  
- `public RefreshRouteModifiers(Unity.Entities.DynamicBuffer<Game.Routes.RouteModifier> modifiers, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies) : System.Void`  
- `public RefreshRouteOptions(Game.Routes.Route& route, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies) : System.Void`  
- `public Update(Unity.Entities.SystemBase system) : System.Void`  

