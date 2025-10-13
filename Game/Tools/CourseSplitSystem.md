# Game.Tools.CourseSplitSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CourseSplitSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.ToolReadyBarrier m_ToolReadyBarrier;
    private Game.Net.SearchSystem m_SearchSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.EntityQuery m_CourseQuery;
    private Game.Tools.CourseSplitSystem+TypeHandle __TypeHandle;

    public CourseSplitSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Boolean GetAuxCourse(Game.Tools.NetCourse& courseData, Game.Prefabs.AuxiliaryNet auxiliaryNet, System.Boolean invert);
    private static Game.Tools.CreationDefinition GetAuxDefinition(Game.Tools.CreationDefinition creationDefinition, Game.Prefabs.AuxiliaryNet auxiliaryNet);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.ToolReadyBarrier m_ToolReadyBarrier`  

```csharp
private Game.Tools.ToolReadyBarrier m_ToolReadyBarrier;
```

- `private Game.Net.SearchSystem m_SearchSystem`  

```csharp
private Game.Net.SearchSystem m_SearchSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.EntityQuery m_CourseQuery`  

```csharp
private Unity.Entities.EntityQuery m_CourseQuery;
```

- `private Game.Tools.CourseSplitSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.CourseSplitSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CourseSplitSystem()`  

```csharp
public CourseSplitSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private static GetAuxCourse(Game.Tools.NetCourse& courseData, Game.Prefabs.AuxiliaryNet auxiliaryNet, System.Boolean invert) : System.Boolean`  

```csharp
private static System.Boolean GetAuxCourse(Game.Tools.NetCourse& courseData, Game.Prefabs.AuxiliaryNet auxiliaryNet, System.Boolean invert);
```

- `private static GetAuxDefinition(Game.Tools.CreationDefinition creationDefinition, Game.Prefabs.AuxiliaryNet auxiliaryNet) : Game.Tools.CreationDefinition`  

```csharp
private static Game.Tools.CreationDefinition GetAuxDefinition(Game.Tools.CreationDefinition creationDefinition, Game.Prefabs.AuxiliaryNet auxiliaryNet);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


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

