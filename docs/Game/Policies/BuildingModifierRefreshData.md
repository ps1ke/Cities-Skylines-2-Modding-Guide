# Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> m_PolicySliderData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingOptionData> m_BuildingOptionData`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.BuildingModifierData> m_BuildingModifierData`  

## Constructors

- `public BuildingModifierRefreshData(Unity.Entities.SystemBase system)`  

## Methods

- `private static AddModifier(Unity.Entities.DynamicBuffer<Game.Buildings.BuildingModifier> modifiers, Game.Prefabs.BuildingModifierData modifierData, System.Single delta) : System.Void`  
- `public RefreshBuildingModifiers(Unity.Entities.DynamicBuffer<Game.Buildings.BuildingModifier> modifiers, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies) : System.Void`  
- `public RefreshBuildingOptions(Game.Buildings.Building& building, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies) : System.Void`  
- `public Update(Unity.Entities.SystemBase system) : System.Void`  

