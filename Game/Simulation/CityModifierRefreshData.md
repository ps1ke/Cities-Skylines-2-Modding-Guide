# Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct CityModifierRefreshData
{
    public Unity.Entities.BufferTypeHandle<Game.Buildings.Efficiency> m_BuildingEfficiencyType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
    public Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType;
    public Unity.Entities.ComponentTypeHandle<Game.Buildings.Signature> m_SignatureType;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> m_PolicySliderData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.CityOptionData> m_CityOptionData;
    public Unity.Entities.BufferLookup<Game.Prefabs.CityModifierData> m_CityModifierData;

    public CityModifierRefreshData(Unity.Entities.SystemBase system);

    private static System.Void AddModifier(Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Game.Prefabs.CityModifierData modifierData, System.Single delta);
    private System.Void AddToTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades);
    public System.Void RefreshCityModifiers(Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies, Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> effectProviderChunks, Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList);
    public System.Void RefreshCityOptions(Game.City.City& city, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies);
    public System.Void Update(Unity.Entities.SystemBase system);
}
```


## Fields

- `public Unity.Entities.BufferTypeHandle<Game.Buildings.Efficiency> m_BuildingEfficiencyType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Buildings.Efficiency> m_BuildingEfficiencyType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.Signature> m_SignatureType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Buildings.Signature> m_SignatureType;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> m_PolicySliderData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PolicySliderData> m_PolicySliderData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.CityOptionData> m_CityOptionData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.CityOptionData> m_CityOptionData;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.CityModifierData> m_CityModifierData`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.CityModifierData> m_CityModifierData;
```


## Constructors

- `public CityModifierRefreshData(Unity.Entities.SystemBase system)`  

```csharp
public CityModifierRefreshData(Unity.Entities.SystemBase system);
```


## Methods

- `private static AddModifier(Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Game.Prefabs.CityModifierData modifierData, System.Single delta) : System.Void`  

```csharp
private static System.Void AddModifier(Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Game.Prefabs.CityModifierData modifierData, System.Single delta);
```

- `private AddToTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades) : System.Void`  

```csharp
private System.Void AddToTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades);
```

- `public RefreshCityModifiers(Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies, Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> effectProviderChunks, Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList) : System.Void`  

```csharp
public System.Void RefreshCityModifiers(Unity.Entities.DynamicBuffer<Game.City.CityModifier> modifiers, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies, Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> effectProviderChunks, Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList);
```

- `public RefreshCityOptions(Game.City.City& city, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies) : System.Void`  

```csharp
public System.Void RefreshCityOptions(Game.City.City& city, Unity.Entities.DynamicBuffer<Game.Policies.Policy> policies);
```

- `public Update(Unity.Entities.SystemBase system) : System.Void`  

```csharp
public System.Void Update(Unity.Entities.SystemBase system);
```


