# Game.Prefabs.UIAvatarColorData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

## Code

```csharp
public sealed struct UIAvatarColorData : Unity.Entities.IBufferElementData
{
    public UnityEngine.Color32 m_Color;

    public UIAvatarColorData(UnityEngine.Color32 color);

}
```


## Fields

- `public UnityEngine.Color32 m_Color`  

```csharp
public UnityEngine.Color32 m_Color;
```


## Constructors

- `public UIAvatarColorData(UnityEngine.Color32 color)`  

```csharp
public UIAvatarColorData(Color32 color)
	{
		m_Color = color;
	}
```


