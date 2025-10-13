# Game.UI.Tooltip.NetCourseTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetCourseTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.NetToolSystem m_NetTool;
    private Unity.Entities.EntityQuery m_NetCourseQuery;
    private Game.UI.Tooltip.TooltipGroup m_Group;
    private Game.UI.Tooltip.FloatTooltip m_Length;
    private Game.UI.Tooltip.FloatTooltip m_Slope;
    private Game.UI.Tooltip.NetCourseTooltipSystem+TypeHandle __TypeHandle;
    private static const System.Single kMinLength;

    public NetCourseTooltipSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static Unity.Mathematics.float3 GetWorldPosition(Unity.Collections.NativeList<Game.Tools.NetCourse> courses, System.Single length);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private static System.Void SortCourses(Unity.Collections.NativeList<Game.Tools.NetCourse> courses);
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.NetToolSystem m_NetTool`  

```csharp
private Game.Tools.NetToolSystem m_NetTool;
```

- `private Unity.Entities.EntityQuery m_NetCourseQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetCourseQuery;
```

- `private Game.UI.Tooltip.TooltipGroup m_Group`  

```csharp
private Game.UI.Tooltip.TooltipGroup m_Group;
```

- `private Game.UI.Tooltip.FloatTooltip m_Length`  

```csharp
private Game.UI.Tooltip.FloatTooltip m_Length;
```

- `private Game.UI.Tooltip.FloatTooltip m_Slope`  

```csharp
private Game.UI.Tooltip.FloatTooltip m_Slope;
```

- `private Game.UI.Tooltip.NetCourseTooltipSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Tooltip.NetCourseTooltipSystem+TypeHandle __TypeHandle;
```

- `private static const System.Single kMinLength`  

```csharp
private static const System.Single kMinLength;
```


## Constructors

- `public NetCourseTooltipSystem()`  

```csharp
public NetCourseTooltipSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private static GetWorldPosition(Unity.Collections.NativeList<Game.Tools.NetCourse> courses, System.Single length) : Unity.Mathematics.float3`  

```csharp
private static Unity.Mathematics.float3 GetWorldPosition(Unity.Collections.NativeList<Game.Tools.NetCourse> courses, System.Single length);
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

- `private static SortCourses(Unity.Collections.NativeList<Game.Tools.NetCourse> courses) : System.Void`  

```csharp
private static System.Void SortCourses(Unity.Collections.NativeList<Game.Tools.NetCourse> courses);
```


## Nested types

- `Game.UI.Tooltip.NetCourseTooltipSystem+TypeHandle`  

