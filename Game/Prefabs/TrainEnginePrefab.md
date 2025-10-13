# Game.Prefabs.TrainEnginePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TrainPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TrainEnginePrefab : Game.Prefabs.TrainPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int32 m_MinEngineCount;
    public System.Int32 m_MaxEngineCount;
    public System.Int32 m_MinCarriagesPerEngine;
    public System.Int32 m_MaxCarriagesPerEngine;
    public Game.Prefabs.TrainCarPrefab m_Tender;

    public TrainEnginePrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_MinEngineCount`  

```csharp
public System.Int32 m_MinEngineCount;
```

- `public System.Int32 m_MaxEngineCount`  

```csharp
public System.Int32 m_MaxEngineCount;
```

- `public System.Int32 m_MinCarriagesPerEngine`  

```csharp
public System.Int32 m_MinCarriagesPerEngine;
```

- `public System.Int32 m_MaxCarriagesPerEngine`  

```csharp
public System.Int32 m_MaxCarriagesPerEngine;
```

- `public Game.Prefabs.TrainCarPrefab m_Tender`  

```csharp
public Game.Prefabs.TrainCarPrefab m_Tender;
```


## Constructors

- `public TrainEnginePrefab()`  

```csharp
public TrainEnginePrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<TrainEngineData>());
		components.Add(ComponentType.ReadWrite<VehicleCarriageElement>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		entityManager.SetComponentData(entity, new TrainEngineData(m_MinEngineCount, m_MaxEngineCount));
		DynamicBuffer<VehicleCarriageElement> buffer = entityManager.GetBuffer<VehicleCarriageElement>(entity);
		if (m_Tender != null)
		{
			Entity entity2 = entityManager.World.GetExistingSystemManaged<PrefabSystem>().GetEntity(m_Tender);
			buffer.Add(new VehicleCarriageElement(entity2, 1, 1, VehicleCarriageDirection.Default));
		}
		buffer.Add(new VehicleCarriageElement(Entity.Null, m_MinCarriagesPerEngine, m_MaxCarriagesPerEngine, VehicleCarriageDirection.Random));
	}
```


