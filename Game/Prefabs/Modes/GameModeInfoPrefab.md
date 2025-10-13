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
public GameModeInfo GetGameModeInfo()
	{
		LocalizedString[] array = null;
		if (m_Descriptions != null)
		{
			array = new LocalizedString[m_Descriptions.Length];
			for (int i = 0; i < m_Descriptions.Length; i++)
			{
				GameModeRule gameModeRule = m_Descriptions[i];
				if (gameModeRule.m_ArgName == string.Empty)
				{
					array[i] = LocalizedString.Id("Menu.GAME_MODE_RULES[" + gameModeRule.m_Term + "]");
					continue;
				}
				array[i] = new LocalizedString("Menu.GAME_MODE_RULES[" + gameModeRule.m_Term + "]", null, new Dictionary<string, ILocElement> { 
				{
					gameModeRule.m_ArgName ?? "",
					new LocalizedNumber<int>(gameModeRule.m_ArgValue, gameModeRule.GetUnit())
				} });
			}
		}
		return new GameModeInfo
		{
			id = ((m_ModeSetting == null) ? "" : m_ModeSetting.prefab.name),
			image = m_Image,
			decorateImage = m_DecorateImage,
			descriptions = (array ?? Array.Empty<LocalizedString>())
		};
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<GameModeInfoData>());
	}
```


