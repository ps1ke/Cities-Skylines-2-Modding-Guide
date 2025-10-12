# Game.UI.InGame.SelectVehiclesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  
- `private Game.UI.ImageSystem m_ImageSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData`  
- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  
- `private Unity.Entities.EntityQuery m_DepotQuery`  
- `private Unity.Entities.Entity <primaryVehicle>k__BackingField`  
- `private Unity.Entities.Entity <secondaryVehicle>k__BackingField`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> <primaryVehicles>k__BackingField`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> <secondaryVehicles>k__BackingField`  
- `private Unity.Collections.NativeArray<System.Int32> m_Results`  
- `private Game.UI.InGame.SelectVehiclesSection+TypeHandle __TypeHandle`  

## Properties

- `protected System.String group { protected get }`  
- `private Unity.Entities.Entity primaryVehicle { private get; private set }`  
- `private Unity.Entities.Entity secondaryVehicle { private get; private set }`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> primaryVehicles { private get; private set }`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> secondaryVehicles { private get; private set }`  

## Constructors

- `public SelectVehiclesSection()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private SetVehicleModel(Unity.Entities.Entity primary, Unity.Entities.Entity secondary) : System.Void`  
- `private Visible() : System.Boolean`  
- `private WriteVehicle(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

## Nested types

- `Game.UI.InGame.SelectVehiclesSection+Result`  
- `Game.UI.InGame.SelectVehiclesSection+DepotsJob`  
- `Game.UI.InGame.SelectVehiclesSection+VehiclesListJob`  
- `Game.UI.InGame.SelectVehiclesSection+TypeHandle`  

