# Game.Prefabs.AreaNameData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct AreaNameData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public UnityEngine.Color32 m_Color;
    public UnityEngine.Color32 m_SelectedColor;

    public static Game.Prefabs.AreaNameData GetDefaults();
}
```


## Fields

- `public UnityEngine.Color32 m_Color`  

```csharp
public UnityEngine.Color32 m_Color;
```

- `public UnityEngine.Color32 m_SelectedColor`  

```csharp
public UnityEngine.Color32 m_SelectedColor;
```


## Methods

- `public static GetDefaults() : Game.Prefabs.AreaNameData`  

```csharp
public static Game.Prefabs.AreaNameData GetDefaults();
```


