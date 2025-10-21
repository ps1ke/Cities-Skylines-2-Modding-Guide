# Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct RouteModifierRefreshData
{
    public Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> m_PolicySliderData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.RouteOptionData> m_RouteOptionData;
    public Unity.Entities.BufferLookup<Game.Prefabs.RouteModifierData> m_RouteModifierData;

    public RouteModifierRefreshData(Unity.Entities.SystemBase system);

    private static System.Void AddModifier(Unity.Entities.DynamicBuffer<Game.Routes.RouteModifier> modifiers, Game.Prefabs.RouteModifierData modifierData, System.Single delta);
    public static System.Void AddModifierData(Game.Routes.RouteModifier& modifier, Game.Prefabs.RouteModifierData modifierData, System.Single delta);
    public static System.Single GetDeltaFromModifier(Game.Routes.RouteModifier modifier, Game.Prefabs.RouteModifierData modifierData);
    public static System.Single GetModifierDelta(Game.Prefabs.RouteModifierData modifierData, System.Single policyAdjustment, Unity.Entities.Entity policy, Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> policySliderData);
    public static System.Single GetPolicyAdjustmentFromModifierDelta(Game.Prefabs.RouteModifierData modifierData, System.Single modifierDelta, Game.Prefabs.PolicySliderData sliderData);
    public System.Void RefreshRouteModifiers(Unity.Entities.DynamicBuffer<Game.Routes.RouteModifier> modifiers, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies);
    public System.Void RefreshRouteOptions(Game.Routes.Route& route, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies);
    public System.Void Update(Unity.Entities.SystemBase system);
}
```


## Fields

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> m_PolicySliderData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> m_PolicySliderData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.RouteOptionData> m_RouteOptionData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.RouteOptionData> m_RouteOptionData;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.RouteModifierData> m_RouteModifierData`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.RouteModifierData> m_RouteModifierData;
```


## Constructors

- `public RouteModifierRefreshData(Unity.Entities.SystemBase system)`  

```csharp
public RouteModifierRefreshData(Unity.Entities.SystemBase system);
```


## Methods

- `private static AddModifier(Unity.Entities.DynamicBuffer<Game.Routes.RouteModifier> modifiers, Game.Prefabs.RouteModifierData modifierData, System.Single delta) : System.Void`  

```csharp
private static System.Void AddModifier(Unity.Entities.DynamicBuffer<Game.Routes.RouteModifier> modifiers, Game.Prefabs.RouteModifierData modifierData, System.Single delta);
```

- `public static AddModifierData(Game.Routes.RouteModifier& modifier, Game.Prefabs.RouteModifierData modifierData, System.Single delta) : System.Void`  

```csharp
public static System.Void AddModifierData(Game.Routes.RouteModifier& modifier, Game.Prefabs.RouteModifierData modifierData, System.Single delta);
```

- `public static GetDeltaFromModifier(Game.Routes.RouteModifier modifier, Game.Prefabs.RouteModifierData modifierData) : System.Single`  

```csharp
public static System.Single GetDeltaFromModifier(Game.Routes.RouteModifier modifier, Game.Prefabs.RouteModifierData modifierData);
```

- `public static GetModifierDelta(Game.Prefabs.RouteModifierData modifierData, System.Single policyAdjustment, Unity.Entities.Entity policy, Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> policySliderData) : System.Single`  

```csharp
public static System.Single GetModifierDelta(Game.Prefabs.RouteModifierData modifierData, System.Single policyAdjustment, Unity.Entities.Entity policy, Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> policySliderData);
```

- `public static GetPolicyAdjustmentFromModifierDelta(Game.Prefabs.RouteModifierData modifierData, System.Single modifierDelta, Game.Prefabs.PolicySliderData sliderData) : System.Single`  

```csharp
public static System.Single GetPolicyAdjustmentFromModifierDelta(Game.Prefabs.RouteModifierData modifierData, System.Single modifierDelta, Game.Prefabs.PolicySliderData sliderData);
```

- `public RefreshRouteModifiers(Unity.Entities.DynamicBuffer<Game.Routes.RouteModifier> modifiers, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies) : System.Void`  

```csharp
public System.Void RefreshRouteModifiers(Unity.Entities.DynamicBuffer<Game.Routes.RouteModifier> modifiers, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies);
```

- `public RefreshRouteOptions(Game.Routes.Route& route, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies) : System.Void`  

```csharp
public System.Void RefreshRouteOptions(Game.Routes.Route& route, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies);
```

- `public Update(Unity.Entities.SystemBase system) : System.Void`  

```csharp
public System.Void Update(Unity.Entities.SystemBase system);
```


