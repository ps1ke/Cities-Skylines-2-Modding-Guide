# Game.Prefabs.AreaColorData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct AreaColorData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public UnityEngine.Color32 m_FillColor;
    public UnityEngine.Color32 m_EdgeColor;
    public UnityEngine.Color32 m_SelectionFillColor;
    public UnityEngine.Color32 m_SelectionEdgeColor;

    public static Game.Prefabs.AreaColorData GetDefaults();
}
```


## Fields

- `public UnityEngine.Color32 m_FillColor`  

```csharp
public UnityEngine.Color32 m_FillColor;
```

- `public UnityEngine.Color32 m_EdgeColor`  

```csharp
public UnityEngine.Color32 m_EdgeColor;
```

- `public UnityEngine.Color32 m_SelectionFillColor`  

```csharp
public UnityEngine.Color32 m_SelectionFillColor;
```

- `public UnityEngine.Color32 m_SelectionEdgeColor`  

```csharp
public UnityEngine.Color32 m_SelectionEdgeColor;
```


## Methods

- `public static GetDefaults() : Game.Prefabs.AreaColorData`  

```csharp
public static AreaColorData GetDefaults()
	{
		return new AreaColorData
		{
			m_FillColor = new Color32(128, 128, 128, 64),
			m_EdgeColor = new Color32(128, 128, 128, 128),
			m_SelectionFillColor = new Color32(128, 128, 128, 128),
			m_SelectionEdgeColor = new Color32(128, 128, 128, byte.MaxValue)
		};
	}
```


