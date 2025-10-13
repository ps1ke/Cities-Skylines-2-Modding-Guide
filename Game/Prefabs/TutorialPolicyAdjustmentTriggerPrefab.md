# Game.Prefabs.TutorialPolicyAdjustmentTriggerPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TutorialTriggerPrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TutorialPolicyAdjustmentTriggerPrefab : Game.Prefabs.TutorialTriggerPrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Tutorials.PolicyAdjustmentTriggerFlags m_Flags;
    public Game.Tutorials.PolicyAdjustmentTriggerTargetFlags m_TargetFlags;

    public TutorialPolicyAdjustmentTriggerPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Tutorials.PolicyAdjustmentTriggerFlags m_Flags`  

```csharp
public Game.Tutorials.PolicyAdjustmentTriggerFlags m_Flags;
```

- `public Game.Tutorials.PolicyAdjustmentTriggerTargetFlags m_TargetFlags`  

```csharp
public Game.Tutorials.PolicyAdjustmentTriggerTargetFlags m_TargetFlags;
```


## Constructors

- `public TutorialPolicyAdjustmentTriggerPrefab()`  

```csharp
public TutorialPolicyAdjustmentTriggerPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


