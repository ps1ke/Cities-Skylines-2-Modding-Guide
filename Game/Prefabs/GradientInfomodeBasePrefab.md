# Game.Prefabs.GradientInfomodeBasePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.InfomodeBasePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IGradientInfomode`  

## Code

```csharp
public abstract class GradientInfomodeBasePrefab : Game.Prefabs.InfomodeBasePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase, Game.Prefabs.IGradientInfomode
{
    public UnityEngine.Color m_Low;
    public UnityEngine.Color m_Medium;
    public UnityEngine.Color m_High;
    public System.Int32 m_Steps;
    public Game.Prefabs.GradientLegendType m_LegendType;
    public System.String m_LowLabelId;
    public System.String m_MediumLabelId;
    public System.String m_HighLabelId;
    private static readonly Game.UI.Localization.CachedLocalizedStringBuilder<System.String> kLabels;

    public UnityEngine.Color lowColor { get; }
    public UnityEngine.Color mediumColor { get; }
    public UnityEngine.Color highColor { get; }
    public Game.Prefabs.GradientLegendType legendType { get; }
    public System.Nullable<Game.UI.Localization.LocalizedString> lowLabel { get; }
    public System.Nullable<Game.UI.Localization.LocalizedString> mediumLabel { get; }
    public System.Nullable<Game.UI.Localization.LocalizedString> highLabel { get; }

    protected GradientInfomodeBasePrefab();

    public virtual System.Void GetColors(UnityEngine.Color& color0, UnityEngine.Color& color1, UnityEngine.Color& color2, System.Single& steps, System.Single& speed, System.Single& tiling, System.Single& fill);
    private static System.Nullable<Game.UI.Localization.LocalizedString> GetLabel(System.String id);
    private static UnityEngine.Color Opaque(UnityEngine.Color color);
}
```


## Fields

- `public UnityEngine.Color m_Low`  

```csharp
public UnityEngine.Color m_Low;
```

- `public UnityEngine.Color m_Medium`  

```csharp
public UnityEngine.Color m_Medium;
```

- `public UnityEngine.Color m_High`  

```csharp
public UnityEngine.Color m_High;
```

- `public System.Int32 m_Steps`  

```csharp
public System.Int32 m_Steps;
```

- `public Game.Prefabs.GradientLegendType m_LegendType`  

```csharp
public Game.Prefabs.GradientLegendType m_LegendType;
```

- `public System.String m_LowLabelId`  

```csharp
public System.String m_LowLabelId;
```

- `public System.String m_MediumLabelId`  

```csharp
public System.String m_MediumLabelId;
```

- `public System.String m_HighLabelId`  

```csharp
public System.String m_HighLabelId;
```

- `private static readonly Game.UI.Localization.CachedLocalizedStringBuilder<System.String> kLabels`  

```csharp
private static readonly Game.UI.Localization.CachedLocalizedStringBuilder<System.String> kLabels;
```


## Properties

- `public UnityEngine.Color lowColor { get }`  

```csharp
public UnityEngine.Color lowColor { get; }
```

- `public UnityEngine.Color mediumColor { get }`  

```csharp
public UnityEngine.Color mediumColor { get; }
```

- `public UnityEngine.Color highColor { get }`  

```csharp
public UnityEngine.Color highColor { get; }
```

- `public Game.Prefabs.GradientLegendType legendType { get }`  

```csharp
public Game.Prefabs.GradientLegendType legendType { get; }
```

- `public System.Nullable<Game.UI.Localization.LocalizedString> lowLabel { get }`  

```csharp
public System.Nullable<Game.UI.Localization.LocalizedString> lowLabel { get; }
```

- `public System.Nullable<Game.UI.Localization.LocalizedString> mediumLabel { get }`  

```csharp
public System.Nullable<Game.UI.Localization.LocalizedString> mediumLabel { get; }
```

- `public System.Nullable<Game.UI.Localization.LocalizedString> highLabel { get }`  

```csharp
public System.Nullable<Game.UI.Localization.LocalizedString> highLabel { get; }
```


## Constructors

- `protected GradientInfomodeBasePrefab()`  

```csharp
protected GradientInfomodeBasePrefab();
```


## Methods

- `public virtual GetColors(UnityEngine.Color& color0, UnityEngine.Color& color1, UnityEngine.Color& color2, System.Single& steps, System.Single& speed, System.Single& tiling, System.Single& fill) : System.Void`  

```csharp
public virtual System.Void GetColors(UnityEngine.Color& color0, UnityEngine.Color& color1, UnityEngine.Color& color2, System.Single& steps, System.Single& speed, System.Single& tiling, System.Single& fill);
```

- `private static GetLabel(System.String id) : System.Nullable<Game.UI.Localization.LocalizedString>`  

```csharp
private static System.Nullable<Game.UI.Localization.LocalizedString> GetLabel(System.String id);
```

- `private static Opaque(UnityEngine.Color color) : UnityEngine.Color`  

```csharp
private static UnityEngine.Color Opaque(UnityEngine.Color color);
```


## Nested types

- `Game.Prefabs.GradientInfomodeBasePrefab+<>c`  

