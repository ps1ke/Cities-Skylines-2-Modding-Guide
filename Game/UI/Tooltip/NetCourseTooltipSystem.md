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
[Preserve]
	public NetCourseTooltipSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `private static GetWorldPosition(Unity.Collections.NativeList<Game.Tools.NetCourse> courses, System.Single length) : Unity.Mathematics.float3`  

```csharp
private static float3 GetWorldPosition(NativeList<NetCourse> courses, float length)
	{
		float num = 0f - length;
		foreach (NetCourse item in courses)
		{
			num += item.m_Length;
			if (num >= 0f && item.m_Length != 0f)
			{
				float t = math.lerp(item.m_StartPosition.m_CourseDelta, item.m_EndPosition.m_CourseDelta, 1f - num / item.m_Length);
				return MathUtils.Position(item.m_Curve, t);
			}
		}
		return courses[courses.Length - 1].m_EndPosition.m_Position;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_NetTool = base.World.GetOrCreateSystemManaged<NetToolSystem>();
		m_NetCourseQuery = GetEntityQuery(ComponentType.ReadOnly<CreationDefinition>(), ComponentType.ReadOnly<NetCourse>());
		RequireForUpdate(m_NetCourseQuery);
		m_Length = new FloatTooltip
		{
			icon = "Media/Glyphs/Length.svg",
			unit = "length"
		};
		m_Slope = new FloatTooltip
		{
			icon = "Media/Glyphs/Slope.svg",
			unit = "percentageSingleFraction",
			signed = true
		};
		m_Group = new TooltipGroup
		{
			path = "tempNetEdgeStart",
			horizontalAlignment = TooltipGroup.Alignment.Center,
			verticalAlignment = TooltipGroup.Alignment.Center,
			category = TooltipGroup.Category.Network
		};
		m_Group.children.Add(m_Length);
		m_Group.children.Add(m_Slope);
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_ToolSystem.activeTool != m_NetTool || m_NetTool.mode == NetToolSystem.Mode.Replace || !(Camera.main != null))
		{
			return;
		}
		CompleteDependency();
		NativeList<NetCourse> courses = new NativeList<NetCourse>(m_NetCourseQuery.CalculateEntityCount(), Allocator.Temp);
		NativeArray<ArchetypeChunk> nativeArray = m_NetCourseQuery.ToArchetypeChunkArray(Allocator.Temp);
		try
		{
			ComponentTypeHandle<NetCourse> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_NetCourse_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<CreationDefinition> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_CreationDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			float num = 0f;
			float num2 = 0f;
			foreach (ArchetypeChunk item in nativeArray)
			{
				NativeArray<NetCourse> nativeArray2 = item.GetNativeArray(ref typeHandle);
				NativeArray<CreationDefinition> nativeArray3 = item.GetNativeArray(ref typeHandle2);
				for (int i = 0; i < nativeArray2.Length; i++)
				{
					NetCourse value = nativeArray2[i];
					CreationDefinition creationDefinition = nativeArray3[i];
					if (!(creationDefinition.m_Original != Entity.Null) && (creationDefinition.m_Flags & (CreationFlags.Permanent | CreationFlags.Delete | CreationFlags.Upgrade | CreationFlags.Invert | CreationFlags.Align)) == 0 && (value.m_StartPosition.m_Flags & CoursePosFlags.IsParallel) == 0)
					{
						num += value.m_Length;
						Bezier4x2 xz = MathUtils.Cut(t: new float2(value.m_StartPosition.m_CourseDelta, value.m_EndPosition.m_CourseDelta), curve: value.m_Curve).xz;
						num2 += MathUtils.Length(xz);
						courses.Add(in value);
					}
				}
			}
			m_Length.value = num2;
			if (courses.Length != 0 && num2 >= 12f)
			{
				float y = courses[0].m_StartPosition.m_Position.y;
				float y2 = courses[courses.Length - 1].m_EndPosition.m_Position.y;
				float num3 = 100f * (y2 - y) / num2;
				m_Slope.value = math.select(num3, 0f, math.abs(num3) < 0.05f);
				SortCourses(courses);
				float length = num / 2f;
				bool onScreen;
				float2 @float = TooltipSystemBase.WorldToTooltipPos(GetWorldPosition(courses, length), out onScreen);
				if (!m_Group.position.Equals(@float))
				{
					m_Group.position = @float;
					m_Group.SetChildrenChanged();
				}
				if (onScreen)
				{
					AddGroup(m_Group);
					return;
				}
				AddMouseTooltip(m_Length);
				AddMouseTooltip(m_Slope);
			}
		}
		finally
		{
			courses.Dispose();
			nativeArray.Dispose();
		}
	}
```

- `private static SortCourses(Unity.Collections.NativeList<Game.Tools.NetCourse> courses) : System.Void`  

```csharp
private static void SortCourses(NativeList<NetCourse> courses)
	{
		NativeArray<NetCourse> nativeArray = courses.AsArray();
		for (int i = 0; i < nativeArray.Length; i++)
		{
			NetCourse value = courses[i];
			if ((value.m_StartPosition.m_Flags & CoursePosFlags.IsFirst) != 0)
			{
				courses[i] = courses[0];
				courses[0] = value;
				break;
			}
		}
		for (int j = 0; j < courses.Length - 1; j++)
		{
			NetCourse netCourse = courses[j];
			for (int k = j + 1; k < courses.Length; k++)
			{
				NetCourse value2 = courses[k];
				if (netCourse.m_EndPosition.m_Position.Equals(value2.m_StartPosition.m_Position))
				{
					courses[k] = courses[j + 1];
					courses[j + 1] = value2;
					break;
				}
			}
		}
	}
```


## Nested types

- `Game.UI.Tooltip.NetCourseTooltipSystem+TypeHandle`  

