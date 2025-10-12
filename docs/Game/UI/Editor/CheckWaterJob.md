# Game.UI.Editor.MapRequirementSystem+CheckWaterJob

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Game.Simulation.WaterSurfaceData m_SurfaceData`  
- `public Unity.Collections.NativeArray<Unity.Entities.Entity> m_StartingTiles`  
- `public Unity.Entities.ComponentLookup<Game.Areas.Geometry> m_GeometryData`  
- `public Colossal.Collections.NativeValue<System.Boolean> m_Result`  

## Methods

- `public Execute() : System.Void`  
- `private HasWater(Colossal.Mathematics.Bounds3 bounds) : System.Boolean`  

