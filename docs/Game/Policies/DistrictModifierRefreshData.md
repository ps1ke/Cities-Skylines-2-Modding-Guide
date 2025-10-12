# Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> m_PolicySliderData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.DistrictOptionData> m_DistrictOptionData`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.DistrictModifierData> m_DistrictModifierData`  

## Constructors

- `public DistrictModifierRefreshData(Unity.Entities.SystemBase system)`  

## Methods

- `private static AddModifier(Unity.Entities.DynamicBuffer<Game.Areas.DistrictModifier> modifiers, Game.Prefabs.DistrictModifierData modifierData, System.Single delta) : System.Void`  
- `public RefreshDistrictModifiers(Unity.Entities.DynamicBuffer<Game.Areas.DistrictModifier> modifiers, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies) : System.Void`  
- `public RefreshDistrictOptions(Game.Areas.District& district, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies) : System.Void`  
- `public Update(Unity.Entities.SystemBase system) : System.Void`  

