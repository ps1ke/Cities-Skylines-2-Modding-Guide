# Game.UI.InGame.DescriptionSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  
- `private System.String <localeId>k__BackingField`  
- `private Unity.Collections.NativeList<Game.Prefabs.LeisureProviderData> m_LeisureDatas`  
- `private Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> m_LocalModifierDatas`  
- `private Unity.Collections.NativeList<Game.Prefabs.CityModifierData> m_CityModifierDatas`  

## Properties

- `protected System.String group { protected get }`  
- `private System.String localeId { private get; private set }`  
- `protected System.Boolean displayForOutsideConnections { protected get }`  
- `protected System.Boolean displayForUnderConstruction { protected get }`  
- `protected System.Boolean displayForUpgrades { protected get }`  

## Constructors

- `public DescriptionSection()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

