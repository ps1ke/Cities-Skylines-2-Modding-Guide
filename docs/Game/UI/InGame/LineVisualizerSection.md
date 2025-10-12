# Game.UI.InGame.LineVisualizerSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private UnityEngine.Color <color>k__BackingField`  
- `private System.Int32 <stopCapacity>k__BackingField`  
- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineStop> <stops>k__BackingField`  
- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineVehicle> <vehicles>k__BackingField`  
- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineSegment> <segments>k__BackingField`  
- `private Unity.Collections.NativeArray<System.Boolean> m_BoolResult`  
- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityResult`  
- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineSegment> m_SegmentsResult`  
- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineStop> m_StopsResult`  
- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineVehicle> m_VehiclesResult`  
- `private Unity.Collections.NativeArray<UnityEngine.Color32> m_ColorResult`  
- `private Unity.Collections.NativeArray<System.Int32> m_StopCapacityResult`  
- `private Game.UI.InGame.LineVisualizerSection+TypeHandle __TypeHandle`  

## Properties

- `protected System.String group { protected get }`  
- `protected System.Boolean displayForDestroyedObjects { protected get }`  
- `protected System.Boolean displayForOutsideConnections { protected get }`  
- `private UnityEngine.Color color { private get; private set }`  
- `private System.Int32 stopCapacity { private get; private set }`  
- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineStop> stops { private get; private set }`  
- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineVehicle> vehicles { private get; private set }`  
- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineSegment> segments { private get; private set }`  

## Constructors

- `public LineVisualizerSection()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  

## Nested types

- `Game.UI.InGame.LineVisualizerSection+LineStop`  
- `Game.UI.InGame.LineVisualizerSection+LineVehicle`  
- `Game.UI.InGame.LineVisualizerSection+LineSegment`  
- `Game.UI.InGame.LineVisualizerSection+Result`  
- `Game.UI.InGame.LineVisualizerSection+VisibilityJob`  
- `Game.UI.InGame.LineVisualizerSection+UpdateJob`  
- `Game.UI.InGame.LineVisualizerSection+TypeHandle`  

