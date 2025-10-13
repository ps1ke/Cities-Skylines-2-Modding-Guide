# Game.Tools.RouteToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RouteToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private System.Boolean <underground>k__BackingField;
    private System.Boolean <serviceUpgrade>k__BackingField;
    private Game.Audio.AudioManager m_AudioManager;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_TempRouteQuery;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Game.Input.IProxyAction m_AddWaypoint;
    private Game.Input.IProxyAction m_InsertWaypoint;
    private Game.Input.IProxyAction m_MoveWaypoint;
    private Game.Input.IProxyAction m_MergeWaypoint;
    private Game.Input.IProxyAction m_RemoveWaypoint;
    private Game.Input.IProxyAction m_UndoWaypoint;
    private Game.Input.IProxyAction m_CreateRoute;
    private Game.Input.IProxyAction m_CompleteRoute;
    private Game.Input.IProxyAction m_DeleteRoute;
    private Game.Input.IProxyAction m_DiscardInsertWaypoint;
    private Game.Input.IProxyAction m_DiscardMoveWaypoint;
    private Game.Input.IProxyAction m_DiscardMergeWaypoint;
    private System.Boolean m_ApplyBlocked;
    private Game.Tools.ControlPoint m_LastRaycastPoint;
    private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
    private Colossal.Collections.NativeValue<Game.Tools.RouteToolSystem+Tooltip> m_Tooltip;
    private Game.Tools.RouteToolSystem+State m_State;
    private System.Boolean m_ControlPointsMoved;
    private System.Boolean m_ForceApply;
    private System.Boolean m_ForceCancel;
    private System.Boolean m_CanApplyModify;
    private Game.Tools.ControlPoint m_MoveStartPosition;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Prefabs.RoutePrefab m_SelectedPrefab;
    private Game.Tools.RouteToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public Game.Prefabs.RoutePrefab prefab { get; set; }
    public Game.Tools.RouteToolSystem+State state { get; }
    public Game.Tools.ControlPoint moveStartPosition { get; }
    public Game.Tools.RouteToolSystem+Tooltip tooltip { get; }
    public System.Boolean underground { get; set; }
    public System.Boolean serviceUpgrade { get; private set; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }

    public RouteToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private System.Boolean CheckPathUpdates();
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void ElevationDown();
    public virtual System.Void ElevationScroll();
    public virtual System.Void ElevationUp();
    public Unity.Collections.NativeList<Game.Tools.ControlPoint> GetControlPoints(Unity.Jobs.JobHandle& dependencies);
    private System.Boolean GetPathfindCompleted();
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint);
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate);
    private Unity.Entities.Entity GetUpgradable(Unity.Entities.Entity entity);
    public virtual System.Void InitializeRaycast();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void SetUnderground(System.Boolean underground);
    private Unity.Jobs.JobHandle SnapControlPoints(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity applyTempRoute);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate);
    private virtual System.Void UpdateActions();
    private System.Void UpdateApplyAction();
    private System.Void UpdateCancelAction();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity applyTempRoute);
    private System.Void UpdateSecondaryApplyAction();
}
```


## Fields

- `private System.Boolean <underground>k__BackingField`  

```csharp
private System.Boolean <underground>k__BackingField;
```

- `private System.Boolean <serviceUpgrade>k__BackingField`  

```csharp
private System.Boolean <serviceUpgrade>k__BackingField;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_TempRouteQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempRouteQuery;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Game.Input.IProxyAction m_AddWaypoint`  

```csharp
private Game.Input.IProxyAction m_AddWaypoint;
```

- `private Game.Input.IProxyAction m_InsertWaypoint`  

```csharp
private Game.Input.IProxyAction m_InsertWaypoint;
```

- `private Game.Input.IProxyAction m_MoveWaypoint`  

```csharp
private Game.Input.IProxyAction m_MoveWaypoint;
```

- `private Game.Input.IProxyAction m_MergeWaypoint`  

```csharp
private Game.Input.IProxyAction m_MergeWaypoint;
```

- `private Game.Input.IProxyAction m_RemoveWaypoint`  

```csharp
private Game.Input.IProxyAction m_RemoveWaypoint;
```

- `private Game.Input.IProxyAction m_UndoWaypoint`  

```csharp
private Game.Input.IProxyAction m_UndoWaypoint;
```

- `private Game.Input.IProxyAction m_CreateRoute`  

```csharp
private Game.Input.IProxyAction m_CreateRoute;
```

- `private Game.Input.IProxyAction m_CompleteRoute`  

```csharp
private Game.Input.IProxyAction m_CompleteRoute;
```

- `private Game.Input.IProxyAction m_DeleteRoute`  

```csharp
private Game.Input.IProxyAction m_DeleteRoute;
```

- `private Game.Input.IProxyAction m_DiscardInsertWaypoint`  

```csharp
private Game.Input.IProxyAction m_DiscardInsertWaypoint;
```

- `private Game.Input.IProxyAction m_DiscardMoveWaypoint`  

```csharp
private Game.Input.IProxyAction m_DiscardMoveWaypoint;
```

- `private Game.Input.IProxyAction m_DiscardMergeWaypoint`  

```csharp
private Game.Input.IProxyAction m_DiscardMergeWaypoint;
```

- `private System.Boolean m_ApplyBlocked`  

```csharp
private System.Boolean m_ApplyBlocked;
```

- `private Game.Tools.ControlPoint m_LastRaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_LastRaycastPoint;
```

- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  

```csharp
private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
```

- `private Colossal.Collections.NativeValue<Game.Tools.RouteToolSystem+Tooltip> m_Tooltip`  

```csharp
private Colossal.Collections.NativeValue<Game.Tools.RouteToolSystem+Tooltip> m_Tooltip;
```

- `private Game.Tools.RouteToolSystem+State m_State`  

```csharp
private Game.Tools.RouteToolSystem+State m_State;
```

- `private System.Boolean m_ControlPointsMoved`  

```csharp
private System.Boolean m_ControlPointsMoved;
```

- `private System.Boolean m_ForceApply`  

```csharp
private System.Boolean m_ForceApply;
```

- `private System.Boolean m_ForceCancel`  

```csharp
private System.Boolean m_ForceCancel;
```

- `private System.Boolean m_CanApplyModify`  

```csharp
private System.Boolean m_CanApplyModify;
```

- `private Game.Tools.ControlPoint m_MoveStartPosition`  

```csharp
private Game.Tools.ControlPoint m_MoveStartPosition;
```

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Prefabs.RoutePrefab m_SelectedPrefab`  

```csharp
private Game.Prefabs.RoutePrefab m_SelectedPrefab;
```

- `private Game.Tools.RouteToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.RouteToolSystem+TypeHandle __TypeHandle;
```

- `public static const System.String kToolID`  

```csharp
public static const System.String kToolID;
```


## Properties

- `public System.String toolID { get }`  

```csharp
public System.String toolID { get; }
```

- `public Game.Prefabs.RoutePrefab prefab { get; set }`  

```csharp
public Game.Prefabs.RoutePrefab prefab { get; set; }
```

- `public Game.Tools.RouteToolSystem+State state { get }`  

```csharp
public Game.Tools.RouteToolSystem+State state { get; }
```

- `public Game.Tools.ControlPoint moveStartPosition { get }`  

```csharp
public Game.Tools.ControlPoint moveStartPosition { get; }
```

- `public Game.Tools.RouteToolSystem+Tooltip tooltip { get }`  

```csharp
public Game.Tools.RouteToolSystem+Tooltip tooltip { get; }
```

- `public System.Boolean underground { get; set }`  

```csharp
public System.Boolean underground { get; set; }
```

- `public System.Boolean serviceUpgrade { get; private set }`  

```csharp
public System.Boolean serviceUpgrade { get; private set; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```


## Constructors

- `public RouteToolSystem()`  

```csharp
[Preserve]
	public RouteToolSystem()
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

- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Apply(JobHandle inputDeps, bool singleFrameOnly = false)
	{
		switch (m_State)
		{
		case State.Default:
			if (GetAllowApply() && m_ControlPoints.Length > 0)
			{
				base.applyMode = ApplyMode.Clear;
				ControlPoint value = m_ControlPoints[0];
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_TransportLineStartSound);
				if (base.EntityManager.HasComponent<Route>(value.m_OriginalEntity) && math.any(value.m_ElementIndex >= 0))
				{
					m_State = State.Modify;
					m_ControlPointsMoved = value.m_ElementIndex.y >= 0;
					m_MoveStartPosition = value;
					m_ForceApply = singleFrameOnly;
					m_CanApplyModify = false;
					if (GetRaycastResult(out var controlPoint2))
					{
						m_LastRaycastPoint = controlPoint2;
						m_ControlPoints[0] = controlPoint2;
						inputDeps = SnapControlPoints(inputDeps, Entity.Null);
						JobHandle.ScheduleBatchedJobs();
						inputDeps.Complete();
						ControlPoint other = m_ControlPoints[0];
						m_ControlPointsMoved |= !m_MoveStartPosition.Equals(other);
						inputDeps = UpdateDefinitions(inputDeps, Entity.Null);
					}
					else
					{
						m_Tooltip.value = Tooltip.None;
					}
					return inputDeps;
				}
				if (!value.Equals(default(ControlPoint)))
				{
					m_State = State.Create;
					m_MoveStartPosition = default(ControlPoint);
					if (GetRaycastResult(out var controlPoint3))
					{
						m_LastRaycastPoint = controlPoint3;
						m_ControlPoints.Add(in controlPoint3);
						inputDeps = SnapControlPoints(inputDeps, Entity.Null);
						inputDeps = UpdateDefinitions(inputDeps, Entity.Null);
					}
					else
					{
						m_ControlPoints.Add(in value);
						m_Tooltip.value = Tooltip.None;
					}
					return inputDeps;
				}
				return Update(inputDeps, fullUpdate: false);
			}
			return Update(inputDeps, fullUpdate: false);
		case State.Create:
			if (GetAllowApply() && !m_TempRouteQuery.IsEmptyIgnoreFilter && GetPathfindCompleted())
			{
				RouteData componentData = m_PrefabSystem.GetComponentData<RouteData>(prefab);
				float num = math.distance(m_ControlPoints[m_ControlPoints.Length - 2].m_Position, m_ControlPoints[m_ControlPoints.Length - 1].m_Position);
				float minWaypointDistance = RouteUtils.GetMinWaypointDistance(componentData);
				if (num >= minWaypointDistance)
				{
					Entity applyTempRoute = Entity.Null;
					NativeArray<ArchetypeChunk> nativeArray = m_TempRouteQuery.ToArchetypeChunkArray(Allocator.TempJob);
					ComponentTypeHandle<Route> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Route_RO_ComponentTypeHandle, ref base.CheckedStateRef);
					if ((nativeArray[0].GetNativeArray(ref typeHandle)[0].m_Flags & RouteFlags.Complete) != 0)
					{
						base.applyMode = ApplyMode.Apply;
						m_State = State.Default;
						m_ControlPoints.Clear();
						applyTempRoute = nativeArray[0].GetNativeArray(GetEntityTypeHandle())[0];
						m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_TransportLineCompleteSound);
					}
					else
					{
						m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_TransportLineBuildSound);
						base.applyMode = ApplyMode.Clear;
					}
					nativeArray.Dispose();
					if (GetRaycastResult(out var controlPoint4))
					{
						m_LastRaycastPoint = controlPoint4;
						m_ControlPoints.Add(in controlPoint4);
						inputDeps = SnapControlPoints(inputDeps, applyTempRoute);
						inputDeps = UpdateDefinitions(inputDeps, applyTempRoute);
					}
					else
					{
						m_Tooltip.value = Tooltip.None;
					}
					return inputDeps;
				}
			}
			return Update(inputDeps, fullUpdate: false);
		case State.Modify:
		{
			bool allowApply = GetAllowApply();
			if (!m_ControlPointsMoved && allowApply && m_ControlPoints.Length > 0)
			{
				base.applyMode = ApplyMode.Clear;
				m_State = State.Create;
				m_MoveStartPosition = default(ControlPoint);
				if (GetRaycastResult(out var controlPoint5))
				{
					m_LastRaycastPoint = controlPoint5;
					m_ControlPoints.Add(in controlPoint5);
					inputDeps = SnapControlPoints(inputDeps, Entity.Null);
					inputDeps = UpdateDefinitions(inputDeps, Entity.Null);
				}
				else
				{
					m_ControlPoints.Add(m_ControlPoints[0]);
					m_Tooltip.value = Tooltip.None;
				}
				return inputDeps;
			}
			if (m_CanApplyModify)
			{
				Entity applyTempRoute2 = Entity.Null;
				if (allowApply && !m_TempRouteQuery.IsEmptyIgnoreFilter)
				{
					base.applyMode = ApplyMode.Apply;
					NativeArray<ArchetypeChunk> nativeArray2 = m_TempRouteQuery.ToArchetypeChunkArray(Allocator.TempJob);
					applyTempRoute2 = nativeArray2[0].GetNativeArray(GetEntityTypeHandle())[0];
					nativeArray2.Dispose();
				}
				else
				{
					base.applyMode = ApplyMode.Clear;
				}
				m_State = State.Default;
				m_ControlPoints.Clear();
				if (GetRaycastResult(out var controlPoint6))
				{
					m_LastRaycastPoint = controlPoint6;
					m_ControlPoints.Add(in controlPoint6);
					inputDeps = SnapControlPoints(inputDeps, applyTempRoute2);
					inputDeps = UpdateDefinitions(inputDeps, applyTempRoute2);
				}
				else
				{
					m_Tooltip.value = Tooltip.None;
				}
				return inputDeps;
			}
			m_ForceApply = true;
			return Update(inputDeps, fullUpdate: false);
		}
		case State.Remove:
		{
			m_ControlPoints.Clear();
			base.applyMode = ApplyMode.Clear;
			m_State = State.Default;
			if (GetRaycastResult(out var controlPoint))
			{
				m_LastRaycastPoint = controlPoint;
				m_ControlPoints.Add(in controlPoint);
				inputDeps = SnapControlPoints(inputDeps, Entity.Null);
				inputDeps = UpdateDefinitions(inputDeps, Entity.Null);
			}
			else
			{
				m_Tooltip.value = Tooltip.None;
			}
			return inputDeps;
		}
		default:
			return Update(inputDeps, fullUpdate: false);
		}
	}
```

- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Cancel(JobHandle inputDeps, bool singleFrameOnly = false)
	{
		m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_TransportLineRemoveSound);
		switch (m_State)
		{
		case State.Default:
			if (GetAllowApply() && m_ControlPoints.Length > 0)
			{
				base.applyMode = ApplyMode.Clear;
				ControlPoint controlPoint2 = m_ControlPoints[0];
				if (base.EntityManager.HasComponent<Route>(controlPoint2.m_OriginalEntity) && controlPoint2.m_ElementIndex.x >= 0)
				{
					m_State = State.Remove;
					m_MoveStartPosition = controlPoint2;
					m_ForceCancel = singleFrameOnly;
					if (GetRaycastResult(out var controlPoint3))
					{
						m_LastRaycastPoint = controlPoint3;
						m_ControlPoints[0] = controlPoint3;
						inputDeps = SnapControlPoints(inputDeps, Entity.Null);
						inputDeps = UpdateDefinitions(inputDeps, Entity.Null);
					}
					else
					{
						m_Tooltip.value = Tooltip.None;
					}
					return inputDeps;
				}
				return Update(inputDeps, fullUpdate: false);
			}
			return Update(inputDeps, fullUpdate: false);
		case State.Create:
		{
			m_ControlPoints.RemoveAtSwapBack(m_ControlPoints.Length - 1);
			base.applyMode = ApplyMode.Clear;
			if (m_ControlPoints.Length <= 1)
			{
				m_State = State.Default;
			}
			if (GetRaycastResult(out var controlPoint5))
			{
				m_LastRaycastPoint = controlPoint5;
				m_ControlPoints[m_ControlPoints.Length - 1] = controlPoint5;
				inputDeps = SnapControlPoints(inputDeps, Entity.Null);
				inputDeps = UpdateDefinitions(inputDeps, Entity.Null);
			}
			else if (m_ControlPoints.Length >= 2)
			{
				m_ControlPoints[m_ControlPoints.Length - 1] = m_ControlPoints[m_ControlPoints.Length - 2];
				inputDeps = UpdateDefinitions(inputDeps, Entity.Null);
			}
			else
			{
				m_Tooltip.value = Tooltip.None;
			}
			return inputDeps;
		}
		case State.Modify:
		{
			m_ControlPoints.Clear();
			base.applyMode = ApplyMode.Clear;
			m_State = State.Default;
			if (GetRaycastResult(out var controlPoint4))
			{
				m_LastRaycastPoint = controlPoint4;
				m_ControlPoints.Add(in controlPoint4);
				inputDeps = SnapControlPoints(inputDeps, Entity.Null);
				inputDeps = UpdateDefinitions(inputDeps, Entity.Null);
			}
			else
			{
				m_Tooltip.value = Tooltip.None;
			}
			return inputDeps;
		}
		case State.Remove:
		{
			Entity applyTempRoute = Entity.Null;
			if (GetAllowApply() && !m_TempRouteQuery.IsEmptyIgnoreFilter)
			{
				base.applyMode = ApplyMode.Apply;
				NativeArray<ArchetypeChunk> nativeArray = m_TempRouteQuery.ToArchetypeChunkArray(Allocator.TempJob);
				applyTempRoute = nativeArray[0].GetNativeArray(GetEntityTypeHandle())[0];
				nativeArray.Dispose();
			}
			else
			{
				base.applyMode = ApplyMode.Clear;
			}
			m_State = State.Default;
			m_ControlPoints.Clear();
			if (GetRaycastResult(out var controlPoint))
			{
				m_LastRaycastPoint = controlPoint;
				m_ControlPoints.Add(in controlPoint);
				inputDeps = SnapControlPoints(inputDeps, applyTempRoute);
				inputDeps = UpdateDefinitions(inputDeps, applyTempRoute);
			}
			else
			{
				m_Tooltip.value = Tooltip.None;
			}
			return inputDeps;
		}
		default:
			return Update(inputDeps, fullUpdate: false);
		}
	}
```

- `private CheckPathUpdates() : System.Boolean`  

```csharp
private bool CheckPathUpdates()
	{
		if (m_EventQuery.IsEmptyIgnoreFilter)
		{
			return false;
		}
		NativeArray<ArchetypeChunk> nativeArray = m_EventQuery.ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			ComponentTypeHandle<PathUpdated> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathUpdated_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentLookup<Temp> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				NativeArray<PathUpdated> nativeArray2 = nativeArray[i].GetNativeArray(ref typeHandle);
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					if (componentLookup.HasComponent(nativeArray2[j].m_Owner))
					{
						return true;
					}
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
		return false;
	}
```

- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Clear(JobHandle inputDeps)
	{
		base.applyMode = ApplyMode.Clear;
		return inputDeps;
	}
```

- `public virtual ElevationDown() : System.Void`  

```csharp
public override void ElevationDown()
	{
		underground = true;
	}
```

- `public virtual ElevationScroll() : System.Void`  

```csharp
public override void ElevationScroll()
	{
		underground = !underground;
	}
```

- `public virtual ElevationUp() : System.Void`  

```csharp
public override void ElevationUp()
	{
		underground = false;
	}
```

- `public GetControlPoints(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.ControlPoint>`  

```csharp
public NativeList<ControlPoint> GetControlPoints(out JobHandle dependencies)
	{
		dependencies = base.Dependency;
		return m_ControlPoints;
	}
```

- `private GetPathfindCompleted() : System.Boolean`  

```csharp
private bool GetPathfindCompleted()
	{
		NativeArray<Entity> nativeArray = m_TempRouteQuery.ToEntityArray(Allocator.TempJob);
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				Entity entity = nativeArray[i];
				DynamicBuffer<RouteWaypoint> buffer = base.EntityManager.GetBuffer<RouteWaypoint>(entity, isReadOnly: true);
				DynamicBuffer<RouteSegment> buffer2 = base.EntityManager.GetBuffer<RouteSegment>(entity, isReadOnly: true);
				for (int j = 0; j < buffer2.Length; j++)
				{
					Entity segment = buffer2[j].m_Segment;
					if (base.EntityManager.TryGetComponent<PathTargets>(segment, out var component))
					{
						RouteWaypoint routeWaypoint = buffer[j];
						RouteWaypoint routeWaypoint2 = buffer[math.select(j + 1, 0, j + 1 >= buffer.Length)];
						if (base.EntityManager.TryGetComponent<Position>(routeWaypoint.m_Waypoint, out var component2) && math.distancesq(component.m_ReadyStartPosition, component2.m_Position) >= 1f)
						{
							return false;
						}
						if (base.EntityManager.TryGetComponent<Position>(routeWaypoint2.m_Waypoint, out var component3) && math.distancesq(component.m_ReadyEndPosition, component3.m_Position) >= 1f)
						{
							return false;
						}
					}
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
		return true;
	}
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public override PrefabBase GetPrefab()
	{
		return prefab;
	}
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint) : System.Boolean`  

```csharp
protected override bool GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate)
	{
		if (GetRaycastResult(out var entity, out var hit, out forceUpdate))
		{
			if (base.EntityManager.HasComponent<ConnectedRoute>(hit.m_HitEntity))
			{
				entity = hit.m_HitEntity;
			}
			controlPoint = new ControlPoint(entity, hit);
			return true;
		}
		controlPoint = default(ControlPoint);
		return false;
	}
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate) : System.Boolean`  

```csharp
protected override bool GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate)
	{
		if (GetRaycastResult(out var entity, out var hit, out forceUpdate))
		{
			if (base.EntityManager.HasComponent<ConnectedRoute>(hit.m_HitEntity))
			{
				entity = hit.m_HitEntity;
			}
			controlPoint = new ControlPoint(entity, hit);
			return true;
		}
		controlPoint = default(ControlPoint);
		return false;
	}
```

- `private GetUpgradable(Unity.Entities.Entity entity) : Unity.Entities.Entity`  

```csharp
private Entity GetUpgradable(Entity entity)
	{
		if (base.EntityManager.TryGetComponent<Attached>(entity, out var component))
		{
			return component.m_Parent;
		}
		return entity;
	}
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public override void InitializeRaycast()
	{
		base.InitializeRaycast();
		if (prefab != null)
		{
			bool flag = false;
			RouteData componentData = m_PrefabSystem.GetComponentData<RouteData>(prefab);
			Entity entity = m_PrefabSystem.GetEntity(prefab);
			if ((m_State == State.Modify || m_State == State.Remove) && base.EntityManager.HasComponent<Route>(m_MoveStartPosition.m_OriginalEntity))
			{
				entity = base.EntityManager.GetComponentData<PrefabRef>(m_MoveStartPosition.m_OriginalEntity).m_Prefab;
			}
			RouteConnectionData component2;
			if (base.EntityManager.TryGetComponent<TransportLineData>(entity, out var component))
			{
				m_ToolRaycastSystem.typeMask = TypeMask.StaticObjects | TypeMask.Net | TypeMask.RouteWaypoints;
				m_ToolRaycastSystem.transportType = component.m_TransportType;
				m_ToolRaycastSystem.raycastFlags |= RaycastFlags.BuildingLots;
				if (component.m_PassengerTransport)
				{
					m_ToolRaycastSystem.raycastFlags |= RaycastFlags.Passenger;
				}
				if (component.m_CargoTransport)
				{
					m_ToolRaycastSystem.raycastFlags |= RaycastFlags.Cargo;
				}
				switch (component.m_TransportType)
				{
				case TransportType.Bus:
					m_ToolRaycastSystem.netLayerMask = Layer.Road | Layer.Pathway | Layer.MarkerPathway | Layer.PublicTransportRoad;
					flag = true;
					break;
				case TransportType.Tram:
					m_ToolRaycastSystem.netLayerMask = Layer.Road | Layer.TramTrack | Layer.PublicTransportRoad;
					flag = true;
					break;
				case TransportType.Train:
					m_ToolRaycastSystem.netLayerMask = Layer.TrainTrack;
					flag = true;
					break;
				case TransportType.Subway:
					m_ToolRaycastSystem.netLayerMask = Layer.SubwayTrack;
					flag = true;
					break;
				case TransportType.Ship:
					m_ToolRaycastSystem.netLayerMask = Layer.Waterway;
					break;
				case TransportType.Airplane:
					m_ToolRaycastSystem.netLayerMask = Layer.Taxiway | Layer.MarkerTaxiway;
					break;
				default:
					m_ToolRaycastSystem.netLayerMask = Layer.None;
					break;
				}
			}
			else if (base.EntityManager.TryGetComponent<RouteConnectionData>(entity, out component2))
			{
				m_ToolRaycastSystem.typeMask = TypeMask.StaticObjects | TypeMask.Net | TypeMask.RouteWaypoints;
				m_ToolRaycastSystem.transportType = TransportType.Work;
				m_ToolRaycastSystem.raycastFlags |= RaycastFlags.BuildingLots;
				if ((component2.m_RouteRoadType & RoadTypes.Car) != RoadTypes.None)
				{
					m_ToolRaycastSystem.netLayerMask |= Layer.Road | Layer.Pathway | Layer.MarkerPathway;
				}
				if ((component2.m_RouteRoadType & RoadTypes.Watercraft) != RoadTypes.None)
				{
					m_ToolRaycastSystem.netLayerMask |= Layer.Waterway;
				}
			}
			else
			{
				m_ToolRaycastSystem.typeMask = TypeMask.Terrain | TypeMask.RouteWaypoints;
				m_ToolRaycastSystem.netLayerMask = Layer.None;
			}
			if (flag && underground)
			{
				m_ToolRaycastSystem.collisionMask = CollisionMask.Underground;
			}
			else
			{
				m_ToolRaycastSystem.collisionMask = CollisionMask.OnGround | CollisionMask.Overground;
			}
			if (m_State == State.Default)
			{
				m_ToolRaycastSystem.typeMask |= TypeMask.RouteSegments;
			}
			m_ToolRaycastSystem.routeType = componentData.m_Type;
		}
		else
		{
			m_ToolRaycastSystem.typeMask = TypeMask.None;
			m_ToolRaycastSystem.netLayerMask = Layer.None;
			m_ToolRaycastSystem.routeType = RouteType.None;
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolOutputBarrier = base.World.GetOrCreateSystemManaged<ToolOutputBarrier>();
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_DefinitionQuery = GetDefinitionQuery();
		m_TempRouteQuery = GetEntityQuery(ComponentType.ReadOnly<Route>(), ComponentType.ReadOnly<Temp>());
		m_EventQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Common.Event>(), ComponentType.ReadOnly<PathUpdated>());
		m_SoundQuery = GetEntityQuery(ComponentType.ReadOnly<ToolUXSoundSettingsData>());
		m_AddWaypoint = InputManager.instance.toolActionCollection.GetActionState("Add Waypoint", "RouteToolSystem");
		m_InsertWaypoint = InputManager.instance.toolActionCollection.GetActionState("Insert Waypoint", "RouteToolSystem");
		m_MoveWaypoint = InputManager.instance.toolActionCollection.GetActionState("Move Waypoint", "RouteToolSystem");
		m_MergeWaypoint = InputManager.instance.toolActionCollection.GetActionState("Merge Waypoint", "RouteToolSystem");
		m_RemoveWaypoint = InputManager.instance.toolActionCollection.GetActionState("Remove Waypoint", "RouteToolSystem");
		m_UndoWaypoint = InputManager.instance.toolActionCollection.GetActionState("Undo Waypoint", "RouteToolSystem");
		m_CreateRoute = InputManager.instance.toolActionCollection.GetActionState("Create Route", "RouteToolSystem");
		m_CompleteRoute = InputManager.instance.toolActionCollection.GetActionState("Complete Route", "RouteToolSystem");
		m_DeleteRoute = InputManager.instance.toolActionCollection.GetActionState("Delete Route", "RouteToolSystem");
		m_DiscardInsertWaypoint = InputManager.instance.toolActionCollection.GetActionState("Discard Insert Waypoint", "RouteToolSystem");
		m_DiscardMoveWaypoint = InputManager.instance.toolActionCollection.GetActionState("Discard Move Waypoint", "RouteToolSystem");
		m_DiscardMergeWaypoint = InputManager.instance.toolActionCollection.GetActionState("Discard Merge Waypoint", "RouteToolSystem");
		m_ControlPoints = new NativeList<ControlPoint>(20, Allocator.Persistent);
		m_Tooltip = new NativeValue<Tooltip>(Allocator.Persistent);
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_ControlPoints.Dispose();
		m_Tooltip.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		base.OnStartRunning();
		m_ControlPoints.Clear();
		m_LastRaycastPoint = default(ControlPoint);
		m_State = State.Default;
		m_Tooltip.value = Tooltip.None;
		m_ForceApply = false;
		m_ForceCancel = false;
		m_ApplyBlocked = false;
		base.requireUnderground = false;
		base.requireNetArrows = false;
		base.requireRoutes = RouteType.None;
		base.requireNet = Layer.None;
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		UpdateActions();
		bool flag = m_ForceApply;
		bool flag2 = m_ForceCancel;
		m_ForceApply = false;
		m_ForceCancel = false;
		if (prefab != null)
		{
			allowUnderground = false;
			base.requireUnderground = false;
			base.requireNetArrows = false;
			base.requireNet = Layer.None;
			base.requireStops = TransportType.None;
			RouteData componentData = m_PrefabSystem.GetComponentData<RouteData>(prefab);
			base.requireRoutes = componentData.m_Type;
			if (componentData.m_Type == RouteType.TransportLine)
			{
				TransportLineData componentData2 = m_PrefabSystem.GetComponentData<TransportLineData>(prefab);
				base.requireNetArrows = true;
				switch (componentData2.m_TransportType)
				{
				case TransportType.Bus:
					base.requireNet |= Layer.Road | Layer.Pathway | Layer.MarkerPathway | Layer.PublicTransportRoad;
					allowUnderground = true;
					break;
				case TransportType.Tram:
					base.requireNet |= Layer.Road | Layer.TramTrack | Layer.PublicTransportRoad;
					allowUnderground = true;
					break;
				case TransportType.Train:
					base.requireNet |= Layer.TrainTrack;
					allowUnderground = true;
					break;
				case TransportType.Subway:
					base.requireNet |= Layer.SubwayTrack;
					allowUnderground = true;
					break;
				case TransportType.Ship:
					base.requireNet |= Layer.Waterway;
					break;
				case TransportType.Airplane:
					base.requireNet |= Layer.Taxiway | Layer.MarkerTaxiway;
					break;
				}
				base.requireStops = componentData2.m_TransportType;
			}
			else if (componentData.m_Type == RouteType.WorkRoute)
			{
				RouteConnectionData componentData3 = m_PrefabSystem.GetComponentData<RouteConnectionData>(prefab);
				if ((componentData3.m_RouteRoadType & RoadTypes.Car) != RoadTypes.None)
				{
					base.requireNet |= Layer.Road | Layer.Pathway | Layer.MarkerPathway;
				}
				if ((componentData3.m_RouteRoadType & RoadTypes.Watercraft) != RoadTypes.None)
				{
					base.requireNet |= Layer.Waterway;
				}
				base.requireStops = TransportType.Work;
			}
			if (allowUnderground)
			{
				base.requireUnderground = underground;
			}
			UpdateInfoview(m_PrefabSystem.GetEntity(prefab));
			if (m_State != State.Default && !base.applyAction.enabled)
			{
				m_State = State.Default;
			}
			if ((m_ToolRaycastSystem.raycastFlags & (RaycastFlags.DebugDisable | RaycastFlags.UIDisable)) == 0)
			{
				switch (m_State)
				{
				case State.Default:
				case State.Create:
					if (m_ApplyBlocked)
					{
						if (base.applyAction.WasReleasedThisFrame() || base.secondaryApplyAction.WasReleasedThisFrame())
						{
							m_ApplyBlocked = false;
						}
						return Update(inputDeps, fullUpdate: false);
					}
					if (base.applyAction.WasPressedThisFrame())
					{
						return Apply(inputDeps, base.applyAction.WasReleasedThisFrame());
					}
					if (base.secondaryApplyAction.WasPressedThisFrame())
					{
						return Cancel(inputDeps, base.secondaryApplyAction.WasReleasedThisFrame());
					}
					break;
				case State.Modify:
					if (base.cancelAction.WasPressedThisFrame())
					{
						m_ApplyBlocked = true;
						m_State = State.Default;
						return Update(inputDeps, fullUpdate: true);
					}
					if (flag || base.applyAction.WasReleasedThisFrame())
					{
						return Apply(inputDeps);
					}
					break;
				case State.Remove:
					if (base.cancelAction.WasPressedThisFrame())
					{
						m_ApplyBlocked = true;
						m_State = State.Default;
						return Update(inputDeps, fullUpdate: true);
					}
					if (flag2 || base.secondaryApplyAction.WasReleasedThisFrame())
					{
						return Cancel(inputDeps);
					}
					break;
				}
				return Update(inputDeps, fullUpdate: false);
			}
		}
		else
		{
			base.requireUnderground = false;
			base.requireNetArrows = false;
			base.requireRoutes = RouteType.None;
			base.requireNet = Layer.None;
			UpdateInfoview(Entity.Null);
			m_Tooltip.value = Tooltip.None;
		}
		if (m_State == State.Modify && base.applyAction.WasReleasedThisFrame())
		{
			if ((m_ToolRaycastSystem.raycastFlags & (RaycastFlags.DebugDisable | RaycastFlags.UIDisable)) == 0)
			{
				return Cancel(inputDeps);
			}
			m_ControlPoints.Clear();
			m_State = State.Default;
		}
		else if (m_State == State.Remove && base.secondaryApplyAction.WasReleasedThisFrame())
		{
			if ((m_ToolRaycastSystem.raycastFlags & (RaycastFlags.DebugDisable | RaycastFlags.UIDisable)) == 0)
			{
				return Apply(inputDeps);
			}
			m_ControlPoints.Clear();
			m_State = State.Default;
		}
		return Clear(inputDeps);
	}
```

- `public virtual SetUnderground(System.Boolean underground) : System.Void`  

```csharp
public override void SetUnderground(bool underground)
	{
		this.underground = underground;
	}
```

- `private SnapControlPoints(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity applyTempRoute) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle SnapControlPoints(JobHandle inputDeps, Entity applyTempRoute)
	{
		return IJobExtensions.Schedule(new SnapJob
		{
			m_Snap = GetActualSnap(),
			m_State = m_State,
			m_Prefab = m_PrefabSystem.GetEntity(prefab),
			m_ApplyTempRoute = applyTempRoute,
			m_MoveStartPosition = m_MoveStartPosition,
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRouteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTransportLineData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportLineData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRouteConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrackLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTransportStopData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportStopData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SlaveLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedRoutes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_ConnectedRoute_RO_BufferLookup, ref base.CheckedStateRef),
			m_Waypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_ControlPoints = m_ControlPoints
		}, inputDeps);
	}
```

- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public override bool TrySetPrefab(PrefabBase prefab)
	{
		if (prefab is RoutePrefab routePrefab)
		{
			this.prefab = routePrefab;
			return true;
		}
		return false;
	}
```

- `private Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Update(JobHandle inputDeps, bool fullUpdate)
	{
		bool flag = CheckPathUpdates();
		if (m_State == State.Modify)
		{
			m_CanApplyModify = true;
		}
		if (GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate))
		{
			forceUpdate = forceUpdate || fullUpdate;
			if (m_ControlPoints.Length == 0)
			{
				m_LastRaycastPoint = controlPoint;
				m_ControlPoints.Add(in controlPoint);
				inputDeps = SnapControlPoints(inputDeps, Entity.Null);
				base.applyMode = ApplyMode.Clear;
				return UpdateDefinitions(inputDeps, Entity.Null);
			}
			if (m_LastRaycastPoint.Equals(controlPoint) && !flag && !forceUpdate)
			{
				base.applyMode = ApplyMode.None;
				return inputDeps;
			}
			m_LastRaycastPoint = controlPoint;
			ControlPoint controlPoint2 = m_ControlPoints[m_ControlPoints.Length - 1];
			m_ControlPoints[m_ControlPoints.Length - 1] = controlPoint;
			inputDeps = SnapControlPoints(inputDeps, Entity.Null);
			JobHandle.ScheduleBatchedJobs();
			inputDeps.Complete();
			ControlPoint other = m_ControlPoints[m_ControlPoints.Length - 1];
			if (controlPoint2.EqualsIgnoreHit(other) && !flag && !forceUpdate)
			{
				base.applyMode = ApplyMode.None;
			}
			else
			{
				m_ControlPointsMoved = true;
				base.applyMode = ApplyMode.Clear;
				inputDeps = UpdateDefinitions(inputDeps, Entity.Null);
			}
			return inputDeps;
		}
		if (m_LastRaycastPoint.Equals(controlPoint))
		{
			forceUpdate = forceUpdate || fullUpdate;
			if (flag || forceUpdate)
			{
				base.applyMode = ApplyMode.Clear;
				if (m_ControlPoints.Length > 0)
				{
					return UpdateDefinitions(inputDeps, Entity.Null);
				}
				return inputDeps;
			}
			base.applyMode = ApplyMode.None;
			return inputDeps;
		}
		m_LastRaycastPoint = controlPoint;
		if (m_State == State.Default && m_ControlPoints.Length == 1)
		{
			base.applyMode = ApplyMode.Clear;
			m_ControlPoints[m_ControlPoints.Length - 1] = default(ControlPoint);
			return UpdateDefinitions(inputDeps, Entity.Null);
		}
		if (m_State == State.Modify && m_ControlPoints.Length >= 1)
		{
			m_ControlPointsMoved = true;
			base.applyMode = ApplyMode.Clear;
			m_ControlPoints[m_ControlPoints.Length - 1] = m_MoveStartPosition;
			return UpdateDefinitions(inputDeps, Entity.Null);
		}
		if (m_State == State.Remove && m_ControlPoints.Length >= 1)
		{
			m_ControlPointsMoved = true;
			base.applyMode = ApplyMode.Clear;
			ControlPoint value = m_MoveStartPosition;
			value.m_OriginalEntity = Entity.Null;
			m_ControlPoints[m_ControlPoints.Length - 1] = value;
			return UpdateDefinitions(inputDeps, Entity.Null);
		}
		if (m_ControlPoints.Length >= 2)
		{
			m_ControlPointsMoved = true;
			base.applyMode = ApplyMode.Clear;
			m_ControlPoints[m_ControlPoints.Length - 1] = m_ControlPoints[m_ControlPoints.Length - 2];
			return UpdateDefinitions(inputDeps, Entity.Null);
		}
		m_Tooltip.value = Tooltip.None;
		return inputDeps;
	}
```

- `private virtual UpdateActions() : System.Void`  

```csharp
private protected override void UpdateActions()
	{
		using (ProxyAction.DeferStateUpdating())
		{
			UpdateApplyAction();
			UpdateSecondaryApplyAction();
			UpdateCancelAction();
		}
	}
```

- `private UpdateApplyAction() : System.Void`  

```csharp
private void UpdateApplyAction()
	{
		switch (state)
		{
		case State.Default:
		{
			Route component3;
			DynamicBuffer<RouteWaypoint> buffer2;
			if (m_ControlPoints.Length < 1 || m_ControlPoints[0].Equals(default(ControlPoint)))
			{
				base.applyAction.enabled = base.actionsEnabled;
				base.applyActionOverride = null;
			}
			else if (m_ControlPoints.Length == 1 && base.EntityManager.TryGetComponent<Route>(m_ControlPoints[0].m_OriginalEntity, out component3) && component3.m_Flags == RouteFlags.Complete && base.EntityManager.TryGetBuffer(m_ControlPoints[0].m_OriginalEntity, isReadOnly: true, out buffer2))
			{
				for (int j = 0; j < buffer2.Length; j++)
				{
					Entity waypoint2 = buffer2[j].m_Waypoint;
					if (base.EntityManager.TryGetComponent<Position>(waypoint2, out var component4) && component4.m_Position.Equals(m_ControlPoints[0].m_Position))
					{
						base.applyAction.enabled = base.actionsEnabled;
						base.applyActionOverride = m_MoveWaypoint;
						return;
					}
				}
				base.applyAction.enabled = base.actionsEnabled;
				base.applyActionOverride = m_InsertWaypoint;
			}
			else if (!base.EntityManager.HasComponent<RouteWaypoint>(m_ControlPoints[0].m_OriginalEntity) || !math.any(m_ControlPoints[0].m_ElementIndex >= 0))
			{
				base.applyAction.enabled = base.actionsEnabled;
				base.applyActionOverride = m_CreateRoute;
			}
			else
			{
				base.applyAction.enabled = false;
				base.applyActionOverride = null;
			}
			break;
		}
		case State.Create:
		{
			ref NativeList<ControlPoint> reference = ref m_ControlPoints;
			if (reference[reference.Length - 1].Equals(default(ControlPoint)))
			{
				base.applyAction.enabled = base.actionsEnabled;
				base.applyActionOverride = null;
				break;
			}
			ref NativeList<ControlPoint> reference2 = ref m_ControlPoints;
			ControlPoint controlPoint = reference2[reference2.Length - 1];
			ref float3 position = ref controlPoint.m_Position;
			ref NativeList<ControlPoint> reference3 = ref m_ControlPoints;
			if (!position.Equals(reference3[reference3.Length - 2].m_Position))
			{
				ref NativeList<ControlPoint> reference4 = ref m_ControlPoints;
				if (!reference4[reference4.Length - 1].m_Position.Equals(m_ControlPoints[0].m_Position))
				{
					base.applyAction.enabled = base.actionsEnabled;
					base.applyActionOverride = (GetAllowApply() ? m_AddWaypoint : null);
					break;
				}
			}
			if (m_ControlPoints.Length >= 3)
			{
				ref NativeList<ControlPoint> reference5 = ref m_ControlPoints;
				if (reference5[reference5.Length - 1].m_Position.Equals(m_ControlPoints[0].m_Position))
				{
					base.applyAction.enabled = base.actionsEnabled;
					base.applyActionOverride = (GetAllowApply() ? m_CompleteRoute : null);
					break;
				}
			}
			base.applyAction.enabled = base.actionsEnabled;
			base.applyActionOverride = null;
			break;
		}
		case State.Modify:
		{
			if (base.EntityManager.TryGetComponent<Route>(m_MoveStartPosition.m_OriginalEntity, out var component) && component.m_Flags == RouteFlags.Complete && base.EntityManager.TryGetBuffer(m_MoveStartPosition.m_OriginalEntity, isReadOnly: true, out DynamicBuffer<RouteWaypoint> buffer))
			{
				for (int i = 0; i < buffer.Length; i++)
				{
					Entity waypoint = buffer[i].m_Waypoint;
					if (base.EntityManager.TryGetComponent<Position>(waypoint, out var component2))
					{
						if (!component2.m_Position.Equals(m_MoveStartPosition.m_Position) && component2.m_Position.Equals(m_ControlPoints[0].m_Position))
						{
							base.applyAction.enabled = base.actionsEnabled;
							base.applyActionOverride = m_MergeWaypoint;
							return;
						}
						if (component2.m_Position.Equals(m_MoveStartPosition.m_Position))
						{
							base.applyAction.enabled = base.actionsEnabled;
							base.applyActionOverride = m_MoveWaypoint;
							return;
						}
					}
				}
				base.applyAction.enabled = base.actionsEnabled;
				base.applyActionOverride = m_InsertWaypoint;
			}
			else
			{
				base.applyAction.enabled = false;
				base.applyActionOverride = null;
			}
			break;
		}
		case State.Remove:
			base.applyAction.enabled = base.actionsEnabled;
			base.applyActionOverride = null;
			break;
		default:
			base.applyAction.enabled = false;
			base.applyActionOverride = null;
			break;
		}
	}
```

- `private UpdateCancelAction() : System.Void`  

```csharp
private void UpdateCancelAction()
	{
		if (state == State.Modify)
		{
			if (base.EntityManager.TryGetComponent<Route>(m_MoveStartPosition.m_OriginalEntity, out var component) && component.m_Flags == RouteFlags.Complete && base.EntityManager.TryGetBuffer(m_MoveStartPosition.m_OriginalEntity, isReadOnly: true, out DynamicBuffer<RouteWaypoint> buffer))
			{
				for (int i = 0; i < buffer.Length; i++)
				{
					Entity waypoint = buffer[i].m_Waypoint;
					if (base.EntityManager.TryGetComponent<Position>(waypoint, out var component2))
					{
						if (!component2.m_Position.Equals(m_MoveStartPosition.m_Position) && component2.m_Position.Equals(m_ControlPoints[0].m_Position))
						{
							base.cancelAction.enabled = base.actionsEnabled;
							base.cancelActionOverride = m_DiscardMergeWaypoint;
							return;
						}
						if (component2.m_Position.Equals(m_MoveStartPosition.m_Position))
						{
							base.cancelAction.enabled = base.actionsEnabled;
							base.cancelActionOverride = m_DiscardMoveWaypoint;
							return;
						}
					}
				}
				base.cancelAction.enabled = base.actionsEnabled;
				base.cancelActionOverride = m_DiscardInsertWaypoint;
			}
			else
			{
				base.cancelAction.enabled = false;
				base.cancelActionOverride = null;
			}
		}
		else
		{
			base.cancelAction.enabled = false;
			base.cancelActionOverride = null;
		}
	}
```

- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity applyTempRoute) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateDefinitions(JobHandle inputDeps, Entity applyTempRoute)
	{
		JobHandle jobHandle = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
		if (prefab != null)
		{
			CreateDefinitionsJob jobData = new CreateDefinitionsJob
			{
				m_State = m_State,
				m_Prefab = m_PrefabSystem.GetEntity(prefab),
				m_ApplyTempRoute = applyTempRoute,
				m_MoveStartPosition = m_MoveStartPosition,
				m_PrefabRouteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AttachedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectedRoutes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_ConnectedRoute_RO_BufferLookup, ref base.CheckedStateRef),
				m_Waypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
				m_ControlPoints = m_ControlPoints,
				m_Tooltip = m_Tooltip,
				m_Color = color,
				m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer()
			};
			if (serviceUpgrade)
			{
				jobData.m_ServiceUpgradeOwner = GetUpgradable(m_ToolSystem.selected);
			}
			JobHandle jobHandle2 = IJobExtensions.Schedule(jobData, inputDeps);
			m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle2);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
		}
		return jobHandle;
	}
```

- `private UpdateSecondaryApplyAction() : System.Void`  

```csharp
private void UpdateSecondaryApplyAction()
	{
		switch (state)
		{
		case State.Default:
		{
			if (m_ControlPoints.Length == 1 && base.EntityManager.TryGetComponent<Route>(m_ControlPoints[0].m_OriginalEntity, out var component) && component.m_Flags == RouteFlags.Complete && base.EntityManager.TryGetBuffer(m_ControlPoints[0].m_OriginalEntity, isReadOnly: true, out DynamicBuffer<RouteWaypoint> buffer))
			{
				for (int i = 0; i < buffer.Length; i++)
				{
					Entity waypoint = buffer[i].m_Waypoint;
					if (base.EntityManager.TryGetComponent<Position>(waypoint, out var component2) && component2.m_Position.Equals(m_ControlPoints[0].m_Position))
					{
						base.secondaryApplyAction.enabled = base.actionsEnabled;
						base.secondaryApplyActionOverride = ((buffer.Length >= 3) ? m_RemoveWaypoint : m_DeleteRoute);
						return;
					}
				}
			}
			base.secondaryApplyAction.enabled = false;
			base.secondaryApplyActionOverride = null;
			break;
		}
		case State.Create:
			if (m_ControlPoints.Length > 1)
			{
				base.secondaryApplyAction.enabled = base.actionsEnabled;
				base.secondaryApplyActionOverride = m_UndoWaypoint;
			}
			else
			{
				base.secondaryApplyAction.enabled = base.actionsEnabled;
				base.secondaryApplyActionOverride = null;
			}
			break;
		case State.Remove:
			base.secondaryApplyAction.enabled = base.actionsEnabled;
			base.secondaryApplyActionOverride = m_RemoveWaypoint;
			break;
		default:
			base.secondaryApplyAction.enabled = false;
			base.secondaryApplyActionOverride = null;
			break;
		}
	}
```


## Nested types

- `Game.Tools.RouteToolSystem+State`  
- `Game.Tools.RouteToolSystem+Tooltip`  
- `Game.Tools.RouteToolSystem+SnapJob`  
- `Game.Tools.RouteToolSystem+CreateDefinitionsJob`  
- `Game.Tools.RouteToolSystem+TypeHandle`  
- `Game.Tools.RouteToolSystem+<get_toolActions>d__41`  

