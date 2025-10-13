# Game.Prefabs.EmissiveProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class EmissiveProperties : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Collections.Generic.List<Game.Prefabs.EmissiveProperties+SingleLightMapping> m_SingleLights;
    public System.Collections.Generic.List<Game.Prefabs.EmissiveProperties+MultiLightMapping> m_MultiLights;
    public System.Collections.Generic.List<Game.Prefabs.EmissiveProperties+AnimationProperties> m_AnimationCurves;
    public System.Collections.Generic.List<Game.Prefabs.EmissiveProperties+SignalGroupAnimation> m_SignalGroupAnimations;
    public static const System.Single kIntensityMultiplier;

    public System.Boolean hasSingleLights { get; }
    public System.Boolean hasMultiLights { get; }
    public System.Boolean hasAnyLights { get; }
    public System.Int32 lightsCount { get; }

    public EmissiveProperties();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Int32 GetSingleLightOffset(System.Int32 materialId);
    public System.Boolean IsSingleLightMaterialId(System.Int32 materialId);
}
```


## Fields

- `public System.Collections.Generic.List<Game.Prefabs.EmissiveProperties+SingleLightMapping> m_SingleLights`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.EmissiveProperties+SingleLightMapping> m_SingleLights;
```

- `public System.Collections.Generic.List<Game.Prefabs.EmissiveProperties+MultiLightMapping> m_MultiLights`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.EmissiveProperties+MultiLightMapping> m_MultiLights;
```

- `public System.Collections.Generic.List<Game.Prefabs.EmissiveProperties+AnimationProperties> m_AnimationCurves`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.EmissiveProperties+AnimationProperties> m_AnimationCurves;
```

- `public System.Collections.Generic.List<Game.Prefabs.EmissiveProperties+SignalGroupAnimation> m_SignalGroupAnimations`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.EmissiveProperties+SignalGroupAnimation> m_SignalGroupAnimations;
```

- `public static const System.Single kIntensityMultiplier`  

```csharp
public static const System.Single kIntensityMultiplier;
```


## Properties

- `public System.Boolean hasSingleLights { get }`  

```csharp
public System.Boolean hasSingleLights { get; }
```

- `public System.Boolean hasMultiLights { get }`  

```csharp
public System.Boolean hasMultiLights { get; }
```

- `public System.Boolean hasAnyLights { get }`  

```csharp
public System.Boolean hasAnyLights { get; }
```

- `public System.Int32 lightsCount { get }`  

```csharp
public System.Int32 lightsCount { get; }
```


## Constructors

- `public EmissiveProperties()`  

```csharp
public EmissiveProperties();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<ProceduralLight>());
		if ((m_AnimationCurves != null && m_AnimationCurves.Count != 0) || (m_SignalGroupAnimations != null && m_SignalGroupAnimations.Count != 0))
		{
			components.Add(ComponentType.ReadWrite<LightAnimation>());
		}
	}
```

- `public GetSingleLightOffset(System.Int32 materialId) : System.Int32`  

```csharp
public int GetSingleLightOffset(int materialId)
	{
		int num = 1;
		if (hasMultiLights)
		{
			num += m_MultiLights.Count;
		}
		if (hasSingleLights)
		{
			for (int i = 0; i < m_SingleLights.Count; i++)
			{
				if (m_SingleLights[i].materialId == materialId)
				{
					return num + i;
				}
			}
		}
		return 0;
	}
```

- `public IsSingleLightMaterialId(System.Int32 materialId) : System.Boolean`  

```csharp
public bool IsSingleLightMaterialId(int materialId)
	{
		if (hasSingleLights)
		{
			foreach (SingleLightMapping singleLight in m_SingleLights)
			{
				if (singleLight.materialId == materialId)
				{
					return true;
				}
			}
		}
		return false;
	}
```


## Nested types

- `Game.Prefabs.EmissiveProperties+Purpose`  
- `Game.Prefabs.EmissiveProperties+MultiLightMapping`  
- `Game.Prefabs.EmissiveProperties+SingleLightMapping`  
- `Game.Prefabs.EmissiveProperties+LightProperties`  
- `Game.Prefabs.EmissiveProperties+AnimationProperties`  
- `Game.Prefabs.EmissiveProperties+SignalGroupAnimation`  

