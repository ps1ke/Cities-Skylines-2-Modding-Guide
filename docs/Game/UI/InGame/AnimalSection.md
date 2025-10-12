# Game.UI.InGame.AnimalSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.InGame.AnimalSection+TypeKey <typeKey>k__BackingField`  
- `private Unity.Entities.Entity <ownerEntity>k__BackingField`  
- `private Unity.Entities.Entity <destinationEntity>k__BackingField`  

## Properties

- `protected System.String group { protected get }`  
- `private Game.UI.InGame.AnimalSection+TypeKey typeKey { private get; private set }`  
- `private Unity.Entities.Entity ownerEntity { private get; private set }`  
- `private Unity.Entities.Entity destinationEntity { private get; private set }`  

## Constructors

- `public AnimalSection()`  

## Methods

- `private GetDestination() : Unity.Entities.Entity`  
- `private GetTypeKey() : Game.UI.InGame.AnimalSection+TypeKey`  
- `private GetTypeKeyString(Game.UI.InGame.AnimalSection+TypeKey typeKey) : System.String`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

## Nested types

- `Game.UI.InGame.AnimalSection+TypeKey`  

