# Game.Rendering.UndergroundViewSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Boolean <undergroundOn>k__BackingField`  
- `private System.Boolean <tunnelsOn>k__BackingField`  
- `private System.Boolean <pipelinesOn>k__BackingField`  
- `private System.Boolean <subPipelinesOn>k__BackingField`  
- `private System.Boolean <waterwaysOn>k__BackingField`  
- `private System.Boolean <contourLinesOn>k__BackingField`  
- `private System.Boolean <markersOn>k__BackingField`  
- `private Game.Net.UtilityTypes <utilityTypes>k__BackingField`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Rendering.UtilityLodUpdateSystem m_UtilityLodUpdateSystem`  
- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Unity.Entities.EntityQuery m_InfomodeQuery`  
- `private System.Boolean m_LastWasWaterways`  
- `private System.Boolean m_LastWasMarkers`  
- `private System.Boolean m_Loaded`  
- `private Game.Net.UtilityTypes m_LastUtilityTypes`  
- `private Game.Rendering.UndergroundViewSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.Boolean undergroundOn { get; private set }`  
- `public System.Boolean tunnelsOn { get; private set }`  
- `public System.Boolean pipelinesOn { get; private set }`  
- `public System.Boolean subPipelinesOn { get; private set }`  
- `public System.Boolean waterwaysOn { get; private set }`  
- `public System.Boolean contourLinesOn { get; private set }`  
- `public System.Boolean markersOn { get; private set }`  
- `public Game.Net.UtilityTypes utilityTypes { get; private set }`  

## Constructors

- `public UndergroundViewSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Rendering.UndergroundViewSystem+TypeHandle`  

