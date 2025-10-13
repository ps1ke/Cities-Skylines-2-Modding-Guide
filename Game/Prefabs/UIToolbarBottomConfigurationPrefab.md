# Game.Prefabs.UIToolbarBottomConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class UIToolbarBottomConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.UITrendThresholds m_MoneyTrendThresholds;
    public Game.Prefabs.UITrendThresholds m_PopulationTrendThresholds;

    public UIToolbarBottomConfigurationPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.UITrendThresholds m_MoneyTrendThresholds`  

```csharp
public Game.Prefabs.UITrendThresholds m_MoneyTrendThresholds;
```

- `public Game.Prefabs.UITrendThresholds m_PopulationTrendThresholds`  

```csharp
public Game.Prefabs.UITrendThresholds m_PopulationTrendThresholds;
```


## Constructors

- `public UIToolbarBottomConfigurationPrefab()`  

```csharp
public UIToolbarBottomConfigurationPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<UIToolbarBottomConfigurationData>());
	}
```


