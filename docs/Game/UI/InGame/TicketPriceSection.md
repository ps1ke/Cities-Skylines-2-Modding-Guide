# Game.UI.InGame.TicketPriceSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  
- `private Unity.Entities.Entity m_TicketPricePolicy`  
- `private Unity.Entities.EntityQuery m_ConfigQuery`  
- `private Game.UI.InGame.UIPolicySlider <sliderData>k__BackingField`  

## Properties

- `protected System.String group { protected get }`  
- `private Game.UI.InGame.UIPolicySlider sliderData { private get; private set }`  

## Constructors

- `public TicketPriceSection()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `private OnSetTicketPrice(System.Int32 newPrice) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

