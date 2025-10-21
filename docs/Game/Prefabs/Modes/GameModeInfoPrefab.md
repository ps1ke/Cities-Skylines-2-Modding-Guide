# Game.Prefabs.Modes.GameModeInfoPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class GameModeInfoPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.Modes.ModeSetting m_ModeSetting;
    public System.String m_Image;
    public System.String m_DecorateImage;
    public Game.Prefabs.Modes.GameModeRule[] m_Descriptions;

    public GameModeInfoPrefab();

    public Game.Prefabs.Modes.GameModeInfo GetGameModeInfo();
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.Modes.ModeSetting m_ModeSetting`  

```csharp
public Game.Prefabs.Modes.ModeSetting m_ModeSetting;
```

- `public System.String m_Image`  

```csharp
public System.String m_Image;
```

- `public System.String m_DecorateImage`  

```csharp
public System.String m_DecorateImage;
```

- `public Game.Prefabs.Modes.GameModeRule[] m_Descriptions`  

```csharp
public Game.Prefabs.Modes.GameModeRule[] m_Descriptions;
```


## Constructors

- `public GameModeInfoPrefab()`  

```csharp
public GameModeInfoPrefab();
```


## Methods

- `public GetGameModeInfo() : Game.Prefabs.Modes.GameModeInfo`  

```csharp
public Game.Prefabs.Modes.GameModeInfo GetGameModeInfo();
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


