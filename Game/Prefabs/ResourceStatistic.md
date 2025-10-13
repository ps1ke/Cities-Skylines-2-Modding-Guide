# Game.Prefabs.ResourceStatistic

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ParametricStatistic`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ResourceStatistic : Game.Prefabs.ParametricStatistic, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.ResourcePrefab[] m_Resources;

    public ResourceStatistic();

    public virtual System.String GetParameterName(System.Int32 parameter);
    public virtual System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData> GetParameters();
}
```


## Fields

- `public Game.Prefabs.ResourcePrefab[] m_Resources`  

```csharp
public Game.Prefabs.ResourcePrefab[] m_Resources;
```


## Constructors

- `public ResourceStatistic()`  

```csharp
public ResourceStatistic();
```


## Methods

- `public virtual GetParameterName(System.Int32 parameter) : System.String`  

```csharp
public override string GetParameterName(int parameter)
	{
		return Enum.GetName(typeof(Resource), EconomyUtils.GetResource(parameter));
	}
```

- `public virtual GetParameters() : System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData>`  

```csharp
public override IEnumerable<StatisticParameterData> GetParameters()
	{
		if (m_Resources != null)
		{
			ResourcePrefab[] resources = m_Resources;
			foreach (ResourcePrefab resourcePrefab in resources)
			{
				int resourceIndex = EconomyUtils.GetResourceIndex(EconomyUtils.GetResource(resourcePrefab.m_Resource));
				yield return new StatisticParameterData(resourceIndex, resourcePrefab.m_Color);
			}
		}
	}
```


## Nested types

- `Game.Prefabs.ResourceStatistic+<GetParameters>d__1`  

