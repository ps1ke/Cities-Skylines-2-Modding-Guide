# Game.Prefabs.Modes.UnlockAtStartMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.LocalModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class UnlockAtStartMode : Game.Prefabs.Modes.LocalModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.PrefabBase[] m_Prefabs;
    public Game.Prefabs.PrefabBase m_Requirement;

    public UnlockAtStartMode();

    public virtual System.Void ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Prefabs.PrefabBase[] m_Prefabs`  

```csharp
public Game.Prefabs.PrefabBase[] m_Prefabs;
```

- `public Game.Prefabs.PrefabBase m_Requirement`  

```csharp
public Game.Prefabs.PrefabBase m_Requirement;
```


## Constructors

- `public UnlockAtStartMode()`  

```csharp
public UnlockAtStartMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public virtual System.Void ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
```

- `public virtual RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
```


