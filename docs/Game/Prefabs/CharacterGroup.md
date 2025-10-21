# Game.Prefabs.CharacterGroup

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.RenderPrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public class CharacterGroup : Game.Prefabs.RenderPrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.CharacterGroup+Character[] m_Characters;
    public Game.Prefabs.CharacterGroup+OverrideInfo[] m_Overrides;

    public CharacterGroup();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.CharacterGroup+Character[] m_Characters`  

```csharp
public Game.Prefabs.CharacterGroup+Character[] m_Characters;
```

- `public Game.Prefabs.CharacterGroup+OverrideInfo[] m_Overrides`  

```csharp
public Game.Prefabs.CharacterGroup+OverrideInfo[] m_Overrides;
```


## Constructors

- `public CharacterGroup()`  

```csharp
public CharacterGroup();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


## Nested types

- `Game.Prefabs.CharacterGroup+Character`  
- `Game.Prefabs.CharacterGroup+OverrideInfo`  
- `Game.Prefabs.CharacterGroup+IndexWeight`  
- `Game.Prefabs.CharacterGroup+IndexWeight8`  
- `Game.Prefabs.CharacterGroup+Meta`  

