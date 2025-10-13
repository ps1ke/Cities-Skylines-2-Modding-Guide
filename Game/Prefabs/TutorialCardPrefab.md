# Game.Prefabs.TutorialCardPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TutorialPhasePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TutorialCardPrefab : Game.Prefabs.TutorialPhasePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Boolean m_CenterCard;

    public TutorialCardPrefab();

    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Boolean m_CenterCard`  

```csharp
public System.Boolean m_CenterCard;
```


## Constructors

- `public TutorialCardPrefab()`  

```csharp
public TutorialCardPrefab();
```


## Methods

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new TutorialPhaseData
		{
			m_Type = ((!m_CenterCard) ? TutorialPhaseType.Card : TutorialPhaseType.CenterCard),
			m_OverrideCompletionDelay = m_OverrideCompletionDelay
		});
	}
```


