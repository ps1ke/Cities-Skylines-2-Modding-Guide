# Game.Prefabs.ZoneBuiltRequirementPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.UnlockRequirementPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ZoneBuiltRequirementPrefab : Game.Prefabs.UnlockRequirementPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.ThemePrefab m_RequiredTheme;
    public Game.Prefabs.ZonePrefab m_RequiredZone;
    public Game.Zones.AreaType m_RequiredType;
    public System.Int32 m_MinimumSquares;
    public System.Int32 m_MinimumCount;
    public System.Int32 m_MinimumLevel;

    public ZoneBuiltRequirementPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.ThemePrefab m_RequiredTheme`  

```csharp
public Game.Prefabs.ThemePrefab m_RequiredTheme;
```

- `public Game.Prefabs.ZonePrefab m_RequiredZone`  

```csharp
public Game.Prefabs.ZonePrefab m_RequiredZone;
```

- `public Game.Zones.AreaType m_RequiredType`  

```csharp
public Game.Zones.AreaType m_RequiredType;
```

- `public System.Int32 m_MinimumSquares`  

```csharp
public System.Int32 m_MinimumSquares;
```

- `public System.Int32 m_MinimumCount`  

```csharp
public System.Int32 m_MinimumCount;
```

- `public System.Int32 m_MinimumLevel`  

```csharp
public System.Int32 m_MinimumLevel;
```


## Constructors

- `public ZoneBuiltRequirementPrefab()`  

```csharp
public ZoneBuiltRequirementPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_RequiredTheme != null)
		{
			prefabs.Add(m_RequiredTheme);
		}
		if (m_RequiredZone != null)
		{
			prefabs.Add(m_RequiredZone);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<ZoneBuiltRequirementData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		entityManager.GetBuffer<UnlockRequirement>(entity).Add(new UnlockRequirement(entity, UnlockFlags.RequireAll));
		ZoneBuiltRequirementData componentData = default(ZoneBuiltRequirementData);
		if (m_RequiredTheme != null)
		{
			componentData.m_RequiredTheme = existingSystemManaged.GetEntity(m_RequiredTheme);
		}
		if (m_RequiredZone != null)
		{
			componentData.m_RequiredZone = existingSystemManaged.GetEntity(m_RequiredZone);
		}
		componentData.m_RequiredType = m_RequiredType;
		componentData.m_MinimumSquares = m_MinimumSquares;
		componentData.m_MinimumCount = m_MinimumCount;
		componentData.m_MinimumLevel = (byte)m_MinimumLevel;
		entityManager.SetComponentData(entity, componentData);
	}
```


