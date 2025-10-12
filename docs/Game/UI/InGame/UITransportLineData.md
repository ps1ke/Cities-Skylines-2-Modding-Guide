# Game.UI.InGame.UITransportLineData

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `System.IComparable<Game.UI.InGame.UITransportLineData>`  

**Attributes:** `IsReadOnly`  

## Fields

- `private readonly Unity.Entities.Entity <entity>k__BackingField`  
- `private readonly System.Boolean <active>k__BackingField`  
- `private readonly System.Boolean <visible>k__BackingField`  
- `private readonly System.Boolean <isCargo>k__BackingField`  
- `private readonly UnityEngine.Color32 <color>k__BackingField`  
- `private readonly System.Int32 <schedule>k__BackingField`  
- `private readonly Game.Prefabs.TransportType <type>k__BackingField`  
- `private readonly System.Single <length>k__BackingField`  
- `private readonly System.Int32 <stops>k__BackingField`  
- `private readonly System.Int32 <vehicles>k__BackingField`  
- `private readonly System.Int32 <cargo>k__BackingField`  
- `private readonly System.Single <usage>k__BackingField`  

## Properties

- `public Unity.Entities.Entity entity { get }`  
- `public System.Boolean active { get }`  
- `public System.Boolean visible { get }`  
- `public System.Boolean isCargo { get }`  
- `public UnityEngine.Color32 color { get }`  
- `public System.Int32 schedule { get }`  
- `public Game.Prefabs.TransportType type { get }`  
- `public System.Single length { get }`  
- `public System.Int32 stops { get }`  
- `public System.Int32 vehicles { get }`  
- `public System.Int32 cargo { get }`  
- `public System.Single usage { get }`  

## Constructors

- `public UITransportLineData(Unity.Entities.Entity entity, System.Boolean active, System.Boolean visible, System.Boolean isCargo, Game.Routes.Color color, Game.UI.InGame.RouteSchedule schedule, Game.Prefabs.TransportType type, System.Single length, System.Int32 stops, System.Int32 vehicles, System.Int32 cargo, System.Single usage)`  

## Methods

- `public CompareTo(Game.UI.InGame.UITransportLineData other) : System.Int32`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

