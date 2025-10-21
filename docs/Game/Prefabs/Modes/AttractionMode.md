# Game.Prefabs.Modes.AttractionMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.LocalModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AttractionMode : Game.Prefabs.Modes.LocalModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.Modes.AttractionMode+ModeData[] m_ModeDatas;

    public AttractionMode();

    public virtual System.Void ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Prefabs.Modes.AttractionMode+ModeData[] m_ModeDatas`  

```csharp
public Game.Prefabs.Modes.AttractionMode+ModeData[] m_ModeDatas;
```


## Constructors

- `public AttractionMode()`  

```csharp
public AttractionMode();
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


## Nested types

- `Game.Prefabs.Modes.AttractionMode+ModeData`  

