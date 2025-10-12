# Game.Prefabs.GradientInfomodeBasePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.InfomodeBasePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IGradientInfomode`  

## Fields

- `public UnityEngine.Color m_Low`  
- `public UnityEngine.Color m_Medium`  
- `public UnityEngine.Color m_High`  
- `public System.Int32 m_Steps`  
- `public Game.Prefabs.GradientLegendType m_LegendType`  
- `public System.String m_LowLabelId`  
- `public System.String m_MediumLabelId`  
- `public System.String m_HighLabelId`  
- `private static readonly Game.UI.Localization.CachedLocalizedStringBuilder<System.String> kLabels`  

## Properties

- `public UnityEngine.Color lowColor { get }`  
- `public UnityEngine.Color mediumColor { get }`  
- `public UnityEngine.Color highColor { get }`  
- `public Game.Prefabs.GradientLegendType legendType { get }`  
- `public System.Nullable<Game.UI.Localization.LocalizedString> lowLabel { get }`  
- `public System.Nullable<Game.UI.Localization.LocalizedString> mediumLabel { get }`  
- `public System.Nullable<Game.UI.Localization.LocalizedString> highLabel { get }`  

## Constructors

- `protected GradientInfomodeBasePrefab()`  

## Methods

- `public virtual GetColors(UnityEngine.Color& color0, UnityEngine.Color& color1, UnityEngine.Color& color2, System.Single& steps, System.Single& speed, System.Single& tiling, System.Single& fill) : System.Void`  
- `private static GetLabel(System.String id) : System.Nullable<Game.UI.Localization.LocalizedString>`  
- `private static Opaque(UnityEngine.Color color) : UnityEngine.Color`  

## Nested types

- `Game.Prefabs.GradientInfomodeBasePrefab+<>c`  

