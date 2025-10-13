# Game.Prefabs.CharacterProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CharacterProperties : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.CharacterProperties+BodyPart m_BodyParts;
    public System.String m_CorrectiveAnimationName;
    public System.String m_AnimatedPropName;
    public Game.Prefabs.CharacterOverlay[] m_Overlays;

    public CharacterProperties();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.CharacterProperties+BodyPart m_BodyParts`  

```csharp
public Game.Prefabs.CharacterProperties+BodyPart m_BodyParts;
```

- `public System.String m_CorrectiveAnimationName`  

```csharp
public System.String m_CorrectiveAnimationName;
```

- `public System.String m_AnimatedPropName`  

```csharp
public System.String m_AnimatedPropName;
```

- `public Game.Prefabs.CharacterOverlay[] m_Overlays`  

```csharp
public Game.Prefabs.CharacterOverlay[] m_Overlays;
```


## Constructors

- `public CharacterProperties()`  

```csharp
public CharacterProperties();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_Overlays != null && m_Overlays.Length != 0)
		{
			for (int i = 0; i < m_Overlays.Length; i++)
			{
				prefabs.Add(m_Overlays[i]);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		if (m_Overlays != null && m_Overlays.Length != 0)
		{
			components.Add(ComponentType.ReadWrite<OverlayElement>());
		}
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		if (m_Overlays != null && m_Overlays.Length != 0)
		{
			PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
			DynamicBuffer<OverlayElement> buffer = entityManager.GetBuffer<OverlayElement>(entity);
			int num = 0;
			for (int i = 0; i < m_Overlays.Length; i++)
			{
				CharacterOverlay characterOverlay = m_Overlays[i];
				num = math.max(num, characterOverlay.m_Index + 1);
			}
			buffer.Resize(num, NativeArrayOptions.ClearMemory);
			for (int j = 0; j < m_Overlays.Length; j++)
			{
				CharacterOverlay characterOverlay2 = m_Overlays[j];
				buffer[characterOverlay2.m_Index] = new OverlayElement
				{
					m_Overlay = existingSystemManaged.GetEntity(characterOverlay2),
					m_SortOrder = characterOverlay2.m_SortOrder
				};
			}
		}
	}
```


## Nested types

- `Game.Prefabs.CharacterProperties+BodyPart`  

