# Game.Prefabs.MultipleUnitTrainFrontPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TrainPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class MultipleUnitTrainFrontPrefab : Game.Prefabs.TrainPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int32 m_MinMultipleUnitCount;
    public System.Int32 m_MaxMultipleUnitCount;
    public Game.Prefabs.MultipleUnitTrainCarriageInfo[] m_Carriages;
    public System.Boolean m_AddReversedEndCarriage;

    public MultipleUnitTrainFrontPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_MinMultipleUnitCount`  

```csharp
public System.Int32 m_MinMultipleUnitCount;
```

- `public System.Int32 m_MaxMultipleUnitCount`  

```csharp
public System.Int32 m_MaxMultipleUnitCount;
```

- `public Game.Prefabs.MultipleUnitTrainCarriageInfo[] m_Carriages`  

```csharp
public Game.Prefabs.MultipleUnitTrainCarriageInfo[] m_Carriages;
```

- `public System.Boolean m_AddReversedEndCarriage`  

```csharp
public System.Boolean m_AddReversedEndCarriage;
```


## Constructors

- `public MultipleUnitTrainFrontPrefab()`  

```csharp
public MultipleUnitTrainFrontPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_Carriages != null)
		{
			for (int i = 0; i < m_Carriages.Length; i++)
			{
				prefabs.Add(m_Carriages[i].m_Carriage);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<TrainEngineData>());
		components.Add(ComponentType.ReadWrite<MultipleUnitTrainData>());
		components.Add(ComponentType.ReadWrite<VehicleCarriageElement>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		entityManager.SetComponentData(entity, new TrainEngineData(m_MinMultipleUnitCount, m_MaxMultipleUnitCount));
		DynamicBuffer<VehicleCarriageElement> buffer = entityManager.GetBuffer<VehicleCarriageElement>(entity);
		if (m_Carriages != null)
		{
			PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
			for (int i = 0; i < m_Carriages.Length; i++)
			{
				MultipleUnitTrainCarriageInfo multipleUnitTrainCarriageInfo = m_Carriages[i];
				Entity entity2 = existingSystemManaged.GetEntity(multipleUnitTrainCarriageInfo.m_Carriage);
				buffer.Add(new VehicleCarriageElement(entity2, multipleUnitTrainCarriageInfo.m_MinCount, multipleUnitTrainCarriageInfo.m_MaxCount, multipleUnitTrainCarriageInfo.m_Direction));
			}
		}
		if (m_AddReversedEndCarriage)
		{
			buffer.Add(new VehicleCarriageElement(entity, 1, 1, VehicleCarriageDirection.Reversed));
		}
	}
```


