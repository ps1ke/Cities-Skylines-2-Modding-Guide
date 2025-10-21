# Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct BuildingModifierRefreshData
{
    public Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> m_PolicySliderData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingOptionData> m_BuildingOptionData;
    public Unity.Entities.BufferLookup<Game.Prefabs.BuildingModifierData> m_BuildingModifierData;

    public BuildingModifierRefreshData(Unity.Entities.SystemBase system);

    private static System.Void AddModifier(Unity.Entities.DynamicBuffer<Game.Buildings.BuildingModifier> modifiers, Game.Prefabs.BuildingModifierData modifierData, System.Single delta);
    public System.Void RefreshBuildingModifiers(Unity.Entities.DynamicBuffer<Game.Buildings.BuildingModifier> modifiers, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies);
    public System.Void RefreshBuildingOptions(Game.Buildings.Building& building, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies);
    public System.Void Update(Unity.Entities.SystemBase system);
}
```


## Fields

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> m_PolicySliderData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> m_PolicySliderData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingOptionData> m_BuildingOptionData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingOptionData> m_BuildingOptionData;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.BuildingModifierData> m_BuildingModifierData`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.BuildingModifierData> m_BuildingModifierData;
```


## Constructors

- `public BuildingModifierRefreshData(Unity.Entities.SystemBase system)`  

```csharp
public BuildingModifierRefreshData(Unity.Entities.SystemBase system);
```


## Methods

- `private static AddModifier(Unity.Entities.DynamicBuffer<Game.Buildings.BuildingModifier> modifiers, Game.Prefabs.BuildingModifierData modifierData, System.Single delta) : System.Void`  

```csharp
private static System.Void AddModifier(Unity.Entities.DynamicBuffer<Game.Buildings.BuildingModifier> modifiers, Game.Prefabs.BuildingModifierData modifierData, System.Single delta);
```

- `public RefreshBuildingModifiers(Unity.Entities.DynamicBuffer<Game.Buildings.BuildingModifier> modifiers, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies) : System.Void`  

```csharp
public System.Void RefreshBuildingModifiers(Unity.Entities.DynamicBuffer<Game.Buildings.BuildingModifier> modifiers, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies);
```

- `public RefreshBuildingOptions(Game.Buildings.Building& building, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies) : System.Void`  

```csharp
public System.Void RefreshBuildingOptions(Game.Buildings.Building& building, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies);
```

- `public Update(Unity.Entities.SystemBase system) : System.Void`  

```csharp
public System.Void Update(Unity.Entities.SystemBase system);
```


