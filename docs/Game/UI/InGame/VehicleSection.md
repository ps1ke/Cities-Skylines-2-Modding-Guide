# Game.UI.InGame.VehicleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.InGame.VehicleStateLocaleKey <stateKey>k__BackingField`  
- `private Game.UI.InGame.VehicleUIUtils+EntityWrapper <owner>k__BackingField`  
- `private System.Boolean <fromOutside>k__BackingField`  
- `private Game.UI.InGame.VehicleUIUtils+EntityWrapper <nextStop>k__BackingField`  

## Properties

- `protected Game.UI.InGame.VehicleStateLocaleKey stateKey { protected get; protected set }`  
- `protected Game.UI.InGame.VehicleUIUtils+EntityWrapper owner { protected get; protected set }`  
- `protected System.Boolean fromOutside { protected get; protected set }`  
- `protected Game.UI.InGame.VehicleUIUtils+EntityWrapper nextStop { protected get; protected set }`  
- `protected Unity.Entities.Entity selectedEntity { protected get }`  
- `protected Unity.Entities.Entity selectedPrefab { protected get }`  

## Constructors

- `protected VehicleSection()`  

## Methods

- `protected virtual OnProcess() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  

