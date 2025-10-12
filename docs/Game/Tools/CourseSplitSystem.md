# Game.Tools.CourseSplitSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.ToolReadyBarrier m_ToolReadyBarrier`  
- `private Game.Net.SearchSystem m_SearchSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Unity.Entities.EntityQuery m_CourseQuery`  
- `private Game.Tools.CourseSplitSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CourseSplitSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private static GetAuxCourse(Game.Tools.NetCourse& courseData, Game.Prefabs.AuxiliaryNet auxiliaryNet, System.Boolean invert) : System.Boolean`  
- `private static GetAuxDefinition(Game.Tools.CreationDefinition creationDefinition, Game.Prefabs.AuxiliaryNet auxiliaryNet) : Game.Tools.CreationDefinition`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tools.CourseSplitSystem+IntersectPos`  
- `Game.Tools.CourseSplitSystem+Course`  
- `Game.Tools.CourseSplitSystem+Overlap`  
- `Game.Tools.CourseSplitSystem+CheckCoursesJob`  
- `Game.Tools.CourseSplitSystem+FindOverlapsJob`  
- `Game.Tools.CourseSplitSystem+DequeueOverlapsJob`  
- `Game.Tools.CourseSplitSystem+CheckCourseIntersectionsJob`  
- `Game.Tools.CourseSplitSystem+CourseHeightItem`  
- `Game.Tools.CourseSplitSystem+CourseHeightData`  
- `Game.Tools.CourseSplitSystem+CheckCourseIntersectionResultsJob`  
- `Game.Tools.CourseSplitSystem+TypeHandle`  

