# Game.Tools.NetToolSystem+UpgradeState

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct UpgradeState
{
    public System.Boolean m_IsUpgrading;
    public System.Boolean m_SkipFlags;
    public Game.Net.SubReplacementSide m_SubReplacementSide;
    public Game.Net.SubReplacementType m_SubReplacementType;
    public Game.Prefabs.CompositionFlags m_OldFlags;
    public Game.Prefabs.CompositionFlags m_AddFlags;
    public Game.Prefabs.CompositionFlags m_RemoveFlags;
    public Unity.Entities.Entity m_SubReplacementPrefab;

}
```


## Fields

- `public System.Boolean m_IsUpgrading`  

```csharp
public System.Boolean m_IsUpgrading;
```

- `public System.Boolean m_SkipFlags`  

```csharp
public System.Boolean m_SkipFlags;
```

- `public Game.Net.SubReplacementSide m_SubReplacementSide`  

```csharp
public Game.Net.SubReplacementSide m_SubReplacementSide;
```

- `public Game.Net.SubReplacementType m_SubReplacementType`  

```csharp
public Game.Net.SubReplacementType m_SubReplacementType;
```

- `public Game.Prefabs.CompositionFlags m_OldFlags`  

```csharp
public Game.Prefabs.CompositionFlags m_OldFlags;
```

- `public Game.Prefabs.CompositionFlags m_AddFlags`  

```csharp
public Game.Prefabs.CompositionFlags m_AddFlags;
```

- `public Game.Prefabs.CompositionFlags m_RemoveFlags`  

```csharp
public Game.Prefabs.CompositionFlags m_RemoveFlags;
```

- `public Unity.Entities.Entity m_SubReplacementPrefab`  

```csharp
public Unity.Entities.Entity m_SubReplacementPrefab;
```


