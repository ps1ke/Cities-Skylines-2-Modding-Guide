# Game.Prefabs.UIPollutionConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class UIPollutionConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.UIPollutionThresholds m_GroundPollution;
    public Game.Prefabs.UIPollutionThresholds m_AirPollution;
    public Game.Prefabs.UIPollutionThresholds m_NoisePollution;

    public UIPollutionConfigurationPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.UIPollutionThresholds m_GroundPollution`  

```csharp
public Game.Prefabs.UIPollutionThresholds m_GroundPollution;
```

- `public Game.Prefabs.UIPollutionThresholds m_AirPollution`  

```csharp
public Game.Prefabs.UIPollutionThresholds m_AirPollution;
```

- `public Game.Prefabs.UIPollutionThresholds m_NoisePollution`  

```csharp
public Game.Prefabs.UIPollutionThresholds m_NoisePollution;
```


## Constructors

- `public UIPollutionConfigurationPrefab()`  

```csharp
public UIPollutionConfigurationPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<UIPollutionConfigurationData>());
	}
```


