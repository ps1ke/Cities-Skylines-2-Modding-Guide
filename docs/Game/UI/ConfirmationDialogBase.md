# Game.UI.ConfirmationDialogBase

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Fields

- `private System.Nullable<Game.UI.Localization.LocalizedString> title`  
- `private Game.UI.Localization.LocalizedString message`  
- `private Game.UI.Localization.LocalizedString confirmAction`  
- `private System.Nullable<Game.UI.Localization.LocalizedString> cancelAction`  
- `private Game.UI.Localization.LocalizedString[] otherActions`  
- `private System.Nullable<Game.UI.Localization.LocalizedString> details`  
- `private System.Boolean copyButton`  
- `protected static const System.String kDefaultSkin`  
- `protected static const System.String kParadoxSkin`  

## Properties

- `protected System.String skin { protected get }`  
- `protected System.Boolean dismissible { protected get }`  

## Constructors

- `protected ConfirmationDialogBase(System.Nullable<Game.UI.Localization.LocalizedString> title, Game.UI.Localization.LocalizedString message, System.Nullable<Game.UI.Localization.LocalizedString> details, System.Boolean copyButton, Game.UI.Localization.LocalizedString confirmAction, System.Nullable<Game.UI.Localization.LocalizedString> cancelAction, Game.UI.Localization.LocalizedString[] otherActions)`  

## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

