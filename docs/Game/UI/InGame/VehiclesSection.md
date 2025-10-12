# Game.UI.InGame.VehiclesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField`  
- `private System.Int32 <vehicleCount>k__BackingField`  
- `private System.Int32 <availableVehicleCount>k__BackingField`  
- `private System.Int32 <vehicleCapacity>k__BackingField`  
- `private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> <vehicleList>k__BackingField`  
- `private Unity.Entities.DynamicBuffer<Game.Vehicles.OwnedVehicle> m_Buffer`  
- `private Unity.Entities.Entity m_CompanyEntity`  

## Properties

- `protected System.String group { protected get }`  
- `private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set }`  
- `private System.Int32 vehicleCount { private get; private set }`  
- `private System.Int32 availableVehicleCount { private get; private set }`  
- `private System.Int32 vehicleCapacity { private get; private set }`  
- `private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList { private get; private set }`  

## Constructors

- `public VehiclesSection()`  

## Methods

- `public static AddVehicle(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity vehicle, Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList) : System.Void`  
- `public static BindVehicle(Game.UI.NameSystem nameSystem, Colossal.UI.Binding.IJsonWriter binder, Game.UI.InGame.VehiclesSection+UIVehicle vehicle) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

## Nested types

- `Game.UI.InGame.VehiclesSection+UIVehicle`  

