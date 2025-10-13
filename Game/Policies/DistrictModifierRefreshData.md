# Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct DistrictModifierRefreshData
{
    public Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> m_PolicySliderData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.DistrictOptionData> m_DistrictOptionData;
    public Unity.Entities.BufferLookup<Game.Prefabs.DistrictModifierData> m_DistrictModifierData;

    public DistrictModifierRefreshData(Unity.Entities.SystemBase system);

    private static System.Void AddModifier(Unity.Entities.DynamicBuffer<Game.Areas.DistrictModifier> modifiers, Game.Prefabs.DistrictModifierData modifierData, System.Single delta);
    public System.Void RefreshDistrictModifiers(Unity.Entities.DynamicBuffer<Game.Areas.DistrictModifier> modifiers, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies);
    public System.Void RefreshDistrictOptions(Game.Areas.District& district, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies);
    public System.Void Update(Unity.Entities.SystemBase system);
}
```


## Fields

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> m_PolicySliderData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> m_PolicySliderData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.DistrictOptionData> m_DistrictOptionData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.DistrictOptionData> m_DistrictOptionData;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.DistrictModifierData> m_DistrictModifierData`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.DistrictModifierData> m_DistrictModifierData;
```


## Constructors

- `public DistrictModifierRefreshData(Unity.Entities.SystemBase system)`  

```csharp
public DistrictModifierRefreshData(Unity.Entities.SystemBase system);
```


## Methods

- `private static AddModifier(Unity.Entities.DynamicBuffer<Game.Areas.DistrictModifier> modifiers, Game.Prefabs.DistrictModifierData modifierData, System.Single delta) : System.Void`  

```csharp
private static System.Void AddModifier(Unity.Entities.DynamicBuffer<Game.Areas.DistrictModifier> modifiers, Game.Prefabs.DistrictModifierData modifierData, System.Single delta);
```

- `public RefreshDistrictModifiers(Unity.Entities.DynamicBuffer<Game.Areas.DistrictModifier> modifiers, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies) : System.Void`  

```csharp
public System.Void RefreshDistrictModifiers(Unity.Entities.DynamicBuffer<Game.Areas.DistrictModifier> modifiers, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies);
```

- `public RefreshDistrictOptions(Game.Areas.District& district, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies) : System.Void`  

```csharp
public System.Void RefreshDistrictOptions(Game.Areas.District& district, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies);
```

- `public Update(Unity.Entities.SystemBase system) : System.Void`  

```csharp
public System.Void Update(Unity.Entities.SystemBase system);
```


