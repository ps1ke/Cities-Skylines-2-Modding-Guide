# Game.UI.InGame.ParkingSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Int32 <parkingFee>k__BackingField`  
- `private System.Int32 <parkedCars>k__BackingField`  
- `private System.Int32 <parkingCapacity>k__BackingField`  

## Properties

- `protected System.String group { protected get }`  
- `private System.Int32 parkingFee { private get; private set }`  
- `private System.Int32 parkedCars { private get; private set }`  
- `private System.Int32 parkingCapacity { private get; private set }`  

## Constructors

- `public ParkingSection()`  

## Methods

- `private CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Objects.SubObject> subObjects, System.Int32& laneCount) : System.Void`  
- `private CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets, System.Int32& laneCount) : System.Void`  
- `private CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubLane> subLanes, System.Int32& laneCount) : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

