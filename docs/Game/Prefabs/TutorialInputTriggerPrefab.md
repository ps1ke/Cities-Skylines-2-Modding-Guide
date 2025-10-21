# Game.Prefabs.TutorialInputTriggerPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TutorialTriggerPrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TutorialInputTriggerPrefab : Game.Prefabs.TutorialTriggerPrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.TutorialInputTriggerPrefab+InputAction[] m_Actions;

    public TutorialInputTriggerPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.TutorialInputTriggerPrefab+InputAction[] m_Actions`  

```csharp
public Game.Prefabs.TutorialInputTriggerPrefab+InputAction[] m_Actions;
```


## Constructors

- `public TutorialInputTriggerPrefab()`  

```csharp
public TutorialInputTriggerPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


## Nested types

- `Game.Prefabs.TutorialInputTriggerPrefab+InputAction`  

