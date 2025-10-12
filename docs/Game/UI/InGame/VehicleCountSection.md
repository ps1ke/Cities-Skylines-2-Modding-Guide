# Game.UI.InGame.VehicleCountSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  
- `private Unity.Entities.Entity m_VehicleCountPolicy`  
- `private Unity.Entities.EntityQuery m_ConfigQuery`  
- `private Unity.Collections.NativeArray<System.Int32> m_IntResults`  
- `private Unity.Collections.NativeReference<System.Single> m_DurationResult`  
- `private System.Int32 <vehicleCountMin>k__BackingField`  
- `private System.Int32 <vehicleCountMax>k__BackingField`  
- `private System.Int32 <vehicleCount>k__BackingField`  
- `private System.Int32 <activeVehicles>k__BackingField`  
- `private System.Single <stableDuration>k__BackingField`  
- `private Game.UI.InGame.VehicleCountSection+TypeHandle __TypeHandle`  

## Properties

- `protected System.String group { protected get }`  
- `private System.Int32 vehicleCountMin { private get; private set }`  
- `private System.Int32 vehicleCountMax { private get; private set }`  
- `private System.Int32 vehicleCount { private get; private set }`  
- `private System.Int32 activeVehicles { private get; private set }`  
- `private System.Single stableDuration { private get; private set }`  

## Constructors

- `public VehicleCountSection()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `private OnSetVehicleCount(System.Single newVehicleCount) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

## Nested types

- `Game.UI.InGame.VehicleCountSection+Result`  
- `Game.UI.InGame.VehicleCountSection+CalculateVehicleCountJob`  
- `Game.UI.InGame.VehicleCountSection+TypeHandle`  

