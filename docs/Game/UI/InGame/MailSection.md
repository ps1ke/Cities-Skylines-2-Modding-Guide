# Game.UI.InGame.MailSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Int32 <sortingRate>k__BackingField`  
- `private System.Int32 <sortingCapacity>k__BackingField`  
- `private System.Int32 <localAmount>k__BackingField`  
- `private System.Int32 <unsortedAmount>k__BackingField`  
- `private System.Int32 <outgoingAmount>k__BackingField`  
- `private System.Int32 <storedAmount>k__BackingField`  
- `private System.Int32 <storageCapacity>k__BackingField`  
- `private Game.UI.InGame.MailSection+MailKey <localKey>k__BackingField`  
- `private Game.UI.InGame.MailSection+MailKey <unsortedKey>k__BackingField`  
- `private Game.UI.InGame.MailSection+Type <type>k__BackingField`  

## Properties

- `protected System.String group { protected get }`  
- `private System.Int32 sortingRate { private get; private set }`  
- `private System.Int32 sortingCapacity { private get; private set }`  
- `private System.Int32 localAmount { private get; private set }`  
- `private System.Int32 unsortedAmount { private get; private set }`  
- `private System.Int32 outgoingAmount { private get; private set }`  
- `private System.Int32 storedAmount { private get; private set }`  
- `private System.Int32 storageCapacity { private get; private set }`  
- `private Game.UI.InGame.MailSection+MailKey localKey { private get; private set }`  
- `private Game.UI.InGame.MailSection+MailKey unsortedKey { private get; private set }`  
- `private Game.UI.InGame.MailSection+Type type { private get; private set }`  

## Constructors

- `public MailSection()`  

## Methods

- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

## Nested types

- `Game.UI.InGame.MailSection+MailKey`  
- `Game.UI.InGame.MailSection+Type`  

