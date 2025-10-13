# Game.Prefabs.ColorProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ColorProperties : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Collections.Generic.List<Game.Prefabs.ColorProperties+VariationSet> m_ColorVariations;
    public System.Collections.Generic.List<Game.Prefabs.ColorProperties+ColorChannelBinding> m_ChannelsBinding;
    public System.Collections.Generic.List<Game.Prefabs.ColorProperties+VariationGroup> m_VariationGroups;
    public Unity.Mathematics.int3 m_VariationRanges;
    public Unity.Mathematics.int3 m_AlphaRanges;
    public Game.Rendering.ColorSourceType m_ExternalColorSource;

    public ColorProperties();

    public System.Boolean CanBeModifiedByExternal(System.SByte channel);
    public System.Int32 GetAlpha(Unity.Mathematics.int3 alphas, System.SByte channel, System.Int32 def);
    public System.Single GetAlpha(Unity.Mathematics.float3 alphas, System.SByte channel, System.Single def);
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public UnityEngine.Color GetColor(System.Int32 index, System.SByte channel);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public System.Boolean SanityCheck(System.SByte channel);
}
```


## Fields

- `public System.Collections.Generic.List<Game.Prefabs.ColorProperties+VariationSet> m_ColorVariations`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.ColorProperties+VariationSet> m_ColorVariations;
```

- `public System.Collections.Generic.List<Game.Prefabs.ColorProperties+ColorChannelBinding> m_ChannelsBinding`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.ColorProperties+ColorChannelBinding> m_ChannelsBinding;
```

- `public System.Collections.Generic.List<Game.Prefabs.ColorProperties+VariationGroup> m_VariationGroups`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.ColorProperties+VariationGroup> m_VariationGroups;
```

- `public Unity.Mathematics.int3 m_VariationRanges`  

```csharp
public Unity.Mathematics.int3 m_VariationRanges;
```

- `public Unity.Mathematics.int3 m_AlphaRanges`  

```csharp
public Unity.Mathematics.int3 m_AlphaRanges;
```

- `public Game.Rendering.ColorSourceType m_ExternalColorSource`  

```csharp
public Game.Rendering.ColorSourceType m_ExternalColorSource;
```


## Constructors

- `public ColorProperties()`  

```csharp
public ColorProperties();
```


## Methods

- `public CanBeModifiedByExternal(System.SByte channel) : System.Boolean`  

```csharp
public bool CanBeModifiedByExternal(sbyte channel)
	{
		if (SanityCheck(channel))
		{
			return m_ChannelsBinding[channel].m_CanBeModifiedByExternal;
		}
		return true;
	}
```

- `public GetAlpha(Unity.Mathematics.int3 alphas, System.SByte channel, System.Int32 def) : System.Int32`  

```csharp
public float GetAlpha(float3 alphas, sbyte channel, float def)
	{
		if (SanityCheck(channel))
		{
			return alphas[m_ChannelsBinding[channel].m_ChannelId];
		}
		return def;
	}
```

- `public GetAlpha(Unity.Mathematics.float3 alphas, System.SByte channel, System.Single def) : System.Single`  

```csharp
public float GetAlpha(float3 alphas, sbyte channel, float def)
	{
		if (SanityCheck(channel))
		{
			return alphas[m_ChannelsBinding[channel].m_ChannelId];
		}
		return def;
	}
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public GetColor(System.Int32 index, System.SByte channel) : UnityEngine.Color`  

```csharp
public Color GetColor(int index, sbyte channel)
	{
		if (SanityCheck(channel) && m_ColorVariations.Count > 0)
		{
			index %= m_ColorVariations.Count;
			return m_ColorVariations[index].m_Colors[m_ChannelsBinding[channel].m_ChannelId];
		}
		return Color.white;
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<ColorVariation>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		MeshColorSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<MeshColorSystem>();
		ColorVariation colorVariation = new ColorVariation
		{
			m_GroupID = orCreateSystemManaged.GetColorGroupID(null),
			m_SyncFlags = ColorSyncFlags.None,
			m_ColorSourceType = m_ExternalColorSource,
			m_Probability = 100
		};
		for (int i = 0; i < 3; i++)
		{
			if (CanBeModifiedByExternal((sbyte)i))
			{
				colorVariation.SetExternalChannelIndex(i, m_ChannelsBinding[i].m_ChannelId);
			}
			else
			{
				colorVariation.SetExternalChannelIndex(i, -1);
			}
		}
		int3 @int = math.clamp(m_VariationRanges, 0, 100);
		int3 alphas = math.clamp(m_AlphaRanges, 0, 100);
		colorVariation.m_HueRange = (byte)@int.x;
		colorVariation.m_SaturationRange = (byte)@int.y;
		colorVariation.m_ValueRange = (byte)@int.z;
		colorVariation.m_AlphaRange0 = (byte)GetAlpha(alphas, 0, 0);
		colorVariation.m_AlphaRange1 = (byte)GetAlpha(alphas, 1, 0);
		colorVariation.m_AlphaRange2 = (byte)GetAlpha(alphas, 2, 0);
		DynamicBuffer<ColorVariation> buffer = entityManager.GetBuffer<ColorVariation>(entity);
		buffer.ResizeUninitialized(m_ColorVariations.Count);
		int num = 0;
		bool flag = false;
		if (m_VariationGroups != null)
		{
			for (int j = 0; j < m_VariationGroups.Count; j++)
			{
				VariationGroup variationGroup = m_VariationGroups[j];
				flag |= string.IsNullOrEmpty(variationGroup.m_Name);
				ColorVariation colorVariation2 = colorVariation;
				colorVariation2.m_GroupID = orCreateSystemManaged.GetColorGroupID(variationGroup.m_Name);
				colorVariation2.m_SyncFlags = variationGroup.m_MeshSyncMode;
				colorVariation2.m_Probability = (byte)math.clamp(variationGroup.m_Probability, 0, 100);
				if (variationGroup.m_OverrideRandomness)
				{
					@int = math.clamp(variationGroup.m_VariationRanges, 0, 100);
					alphas = math.clamp(variationGroup.m_AlphaRanges, 0, 100);
					colorVariation2.m_HueRange = (byte)@int.x;
					colorVariation2.m_SaturationRange = (byte)@int.y;
					colorVariation2.m_ValueRange = (byte)@int.z;
					colorVariation2.m_AlphaRange0 = (byte)GetAlpha(alphas, 0, 0);
					colorVariation2.m_AlphaRange1 = (byte)GetAlpha(alphas, 1, 0);
					colorVariation2.m_AlphaRange2 = (byte)GetAlpha(alphas, 2, 0);
				}
				for (int k = 0; k < m_ColorVariations.Count; k++)
				{
					if (m_ColorVariations[k].m_VariationGroup == variationGroup.m_Name)
					{
						ColorVariation value = colorVariation2;
						for (int l = 0; l < 3; l++)
						{
							value.m_ColorSet[l] = GetColor(k, (sbyte)l);
						}
						buffer[num++] = value;
					}
				}
			}
		}
		if (flag)
		{
			return;
		}
		for (int m = 0; m < m_ColorVariations.Count; m++)
		{
			if (string.IsNullOrEmpty(m_ColorVariations[m].m_VariationGroup))
			{
				ColorVariation value2 = colorVariation;
				for (int n = 0; n < 3; n++)
				{
					value2.m_ColorSet[n] = GetColor(m, (sbyte)n);
				}
				buffer[num++] = value2;
			}
		}
	}
```

- `public SanityCheck(System.SByte channel) : System.Boolean`  

```csharp
public bool SanityCheck(sbyte channel)
	{
		if (m_ChannelsBinding != null && channel >= 0)
		{
			return channel < m_ChannelsBinding.Count;
		}
		return false;
	}
```


## Nested types

- `Game.Prefabs.ColorProperties+VariationSet`  
- `Game.Prefabs.ColorProperties+ColorChannelBinding`  
- `Game.Prefabs.ColorProperties+VariationGroup`  

