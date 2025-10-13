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
public static Game.Prefabs.AreaColorData GetDefaults();
```


