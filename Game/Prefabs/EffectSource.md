# Game.Prefabs.EffectSource

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class EffectSource : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Collections.Generic.List<Game.Prefabs.EffectSource+EffectSettings> m_Effects;
    public System.Collections.Generic.List<Game.Prefabs.EffectSource+AnimationProperties> m_AnimationCurves;

    public EffectSource();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Collections.Generic.List<Game.Prefabs.EffectSource+EffectSettings> m_Effects`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.EffectSource+EffectSettings> m_Effects;
```

- `public System.Collections.Generic.List<Game.Prefabs.EffectSource+AnimationProperties> m_AnimationCurves`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.EffectSource+AnimationProperties> m_AnimationCurves;
```


## Constructors

- `public EffectSource()`  

```csharp
public EffectSource();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<EnabledEffect>());
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_Effects == null)
		{
			return;
		}
		foreach (EffectSettings effect in m_Effects)
		{
			prefabs.Add(effect.m_Effect);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Effect>());
		if (m_AnimationCurves != null && m_AnimationCurves.Count != 0)
		{
			components.Add(ComponentType.ReadWrite<EffectAnimation>());
		}
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		if (m_Effects != null)
		{
			DynamicBuffer<Effect> buffer = entityManager.GetBuffer<Effect>(entity);
			buffer.EnsureCapacity(m_Effects.Count);
			for (int i = 0; i < m_Effects.Count; i++)
			{
				EffectSettings effectSettings = m_Effects[i];
				if (!(effectSettings.m_Effect == null))
				{
					if (effectSettings.m_Intensity == 0f)
					{
						effectSettings.m_Intensity = 1f;
					}
					buffer.Add(new Effect
					{
						m_Effect = existingSystemManaged.GetEntity(effectSettings.m_Effect),
						m_Position = effectSettings.m_PositionOffset,
						m_Rotation = effectSettings.m_Rotation,
						m_Scale = effectSettings.m_Scale,
						m_Intensity = effectSettings.m_Intensity,
						m_ParentMesh = effectSettings.m_ParentMesh,
						m_AnimationIndex = effectSettings.m_AnimationIndex
					});
				}
			}
		}
		if (m_AnimationCurves != null && m_AnimationCurves.Count != 0)
		{
			DynamicBuffer<EffectAnimation> buffer2 = entityManager.GetBuffer<EffectAnimation>(entity);
			buffer2.ResizeUninitialized(m_AnimationCurves.Count);
			for (int j = 0; j < m_AnimationCurves.Count; j++)
			{
				AnimationProperties animationProperties = m_AnimationCurves[j];
				buffer2[j] = new EffectAnimation
				{
					m_DurationFrames = (uint)Mathf.RoundToInt(animationProperties.m_Duration * 60f),
					m_AnimationCurve = new AnimationCurve1(animationProperties.m_Curve)
				};
			}
		}
	}
```


## Nested types

- `Game.Prefabs.EffectSource+EffectSettings`  
- `Game.Prefabs.EffectSource+AnimationProperties`  

