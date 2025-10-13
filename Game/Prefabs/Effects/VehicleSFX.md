# Game.Prefabs.Effects.VehicleSFX

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Effects`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class VehicleSFX : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Unity.Mathematics.float2 m_SpeedLimits;
    public Unity.Mathematics.float2 m_SpeedPitches;
    public Unity.Mathematics.float2 m_SpeedVolumes;

    public VehicleSFX();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Unity.Mathematics.float2 m_SpeedLimits`  

```csharp
public Unity.Mathematics.float2 m_SpeedLimits;
```

- `public Unity.Mathematics.float2 m_SpeedPitches`  

```csharp
public Unity.Mathematics.float2 m_SpeedPitches;
```

- `public Unity.Mathematics.float2 m_SpeedVolumes`  

```csharp
public Unity.Mathematics.float2 m_SpeedVolumes;
```


## Constructors

- `public VehicleSFX()`  

```csharp
public VehicleSFX();
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
		components.Add(ComponentType.ReadWrite<VehicleAudioEffectData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		VehicleAudioEffectData componentData = new VehicleAudioEffectData
		{
			m_SpeedLimits = m_SpeedLimits,
			m_SpeedPitches = m_SpeedPitches,
			m_SpeedVolumes = m_SpeedVolumes
		};
		entityManager.SetComponentData(entity, componentData);
	}
```


