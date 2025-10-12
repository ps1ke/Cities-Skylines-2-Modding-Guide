# Colossal.UI.UIView+Settings

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Fields

- `public System.UInt32 width`  
- `public System.UInt32 height`  
- `public System.Boolean acceptsInput`  
- `public System.Boolean enableComplexTextLayout`  
- `public System.Boolean enableComplexCSSSelectorsStyling`  
- `public System.Boolean isTransparent`  
- `public System.Boolean pixelPerfect`  
- `public System.Boolean liveReload`  
- `public System.String liveReloadUrl`  
- `public System.Int32 devServerPort`  
- `public System.Boolean wideTextures`  
- `public System.Boolean enableBackdropFilter`  
- `private Colossal.UI.ViewListener m_Listener`  
- `private Colossal.UI.TextInputHandler m_TextInputHandler`  

## Properties

- `public static Colossal.UI.UIView+Settings New { get }`  
- `public Colossal.UI.ViewListener listener { get; set }`  
- `public Colossal.UI.TextInputHandler textInputHandler { get; set }`  

## Methods

- `public Dispose() : System.Void`  
- `public ToNativeSettings() : cohtml.Net.ViewSettings`  

