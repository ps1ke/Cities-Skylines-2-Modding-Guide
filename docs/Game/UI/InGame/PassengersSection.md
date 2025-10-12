# Game.UI.InGame.PassengersSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Int32 <passengers>k__BackingField`  
- `private System.Int32 <maxPassengers>k__BackingField`  
- `private System.Int32 <pets>k__BackingField`  
- `private Game.UI.InGame.VehiclePassengerLocaleKey <vehiclePassengerKey>k__BackingField`  

## Properties

- `protected System.String group { protected get }`  
- `private System.Int32 passengers { private get; private set }`  
- `private System.Int32 maxPassengers { private get; private set }`  
- `private System.Int32 pets { private get; private set }`  
- `private Game.UI.InGame.VehiclePassengerLocaleKey vehiclePassengerKey { private get; private set }`  
- `protected Unity.Entities.Entity selectedEntity { protected get }`  
- `protected Unity.Entities.Entity selectedPrefab { protected get }`  

## Constructors

- `public PassengersSection()`  

## Methods

- `private AddPassengerCapacity(Unity.Entities.Entity prefab) : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

