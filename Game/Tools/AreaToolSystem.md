# Game.Tools.AreaToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private Game.Tools.AreaToolSystem+Mode <mode>k__BackingField;
    private Unity.Entities.Entity <recreate>k__BackingField;
    private System.Boolean <underground>k__BackingField;
    private System.Boolean <allowGenerate>k__BackingField;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Input.IProxyAction m_AddAreaNode;
    private Game.Input.IProxyAction m_InsertAreaNode;
    private Game.Input.IProxyAction m_MergeAreaNode;
    private Game.Input.IProxyAction m_MoveAreaNode;
    private Game.Input.IProxyAction m_DeleteAreaNode;
    private Game.Input.IProxyAction m_UndoAreaNode;
    private Game.Input.IProxyAction m_CompleteArea;
    private Game.Input.IProxyAction m_CreateArea;
    private Game.Input.IProxyAction m_DeleteArea;
    private Game.Input.IProxyAction m_DiscardInsertAreaNode;
    private Game.Input.IProxyAction m_DiscardMoveAreaNode;
    private Game.Input.IProxyAction m_DiscardMergeAreaNode;
    private Game.Input.IProxyAction m_CreateAreaOrMoveAreaNode;
    private Game.Input.IProxyAction m_CreateAreaOrInsertAreaNode;
    private System.Boolean m_ApplyBlocked;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_TempAreaQuery;
    private Unity.Entities.EntityQuery m_TempBuildingQuery;
    private Unity.Entities.EntityQuery m_MapTileQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Game.Tools.ControlPoint m_LastRaycastPoint;
    private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
    private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_MoveStartPositions;
    private Colossal.Collections.NativeValue<Game.Tools.AreaToolSystem+Tooltip> m_Tooltip;
    private Game.Tools.AreaToolSystem+Mode m_LastMode;
    private Game.Tools.AreaToolSystem+State m_State;
    private Game.Prefabs.AreaPrefab m_Prefab;
    private System.Boolean m_ControlPointsMoved;
    private System.Boolean m_AllowCreateArea;
    private System.Boolean m_ForceCancel;
    private Game.Tools.AreaToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public System.Int32 uiModeIndex { get; }
    public Game.Tools.AreaToolSystem+Mode mode { get; set; }
    public Game.Tools.AreaToolSystem+Mode actualMode { get; }
    public Unity.Entities.Entity recreate { get; set; }
    public System.Boolean underground { get; set; }
    public System.Boolean allowGenerate { get; private set; }
    public Game.Tools.AreaToolSystem+State state { get; }
    public Game.Tools.AreaToolSystem+Tooltip tooltip { get; }
    public Game.Prefabs.AreaPrefab prefab { get; set; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }

    public AreaToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void ElevationDown();
    public virtual System.Void ElevationScroll();
    public virtual System.Void ElevationUp();
    public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    private static System.Void GetAvailableSnapMask(Game.Prefabs.AreaGeometryData prefabAreaData, System.Boolean editorMode, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    public Unity.Collections.NativeList<Game.Tools.ControlPoint> GetControlPoints(Unity.Collections.NativeList`1[[Game.Tools.ControlPoint, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& moveStartPositions, Unity.Jobs.JobHandle& dependencies);
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    public virtual System.Void GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes);
    public virtual System.Void InitializeRaycast();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnStopRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void SetUnderground(System.Boolean underground);
    private Unity.Jobs.JobHandle SnapControlPoints(Unity.Jobs.JobHandle inputDeps, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempAreas);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate);
    private virtual System.Void UpdateActions();
    private System.Void UpdateApplyAction();
    private System.Void UpdateCancelAction();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempAreas, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempBuildings);
    private System.Void UpdateSecondaryApplyAction();
}
```


## Fields

- `private Game.Tools.AreaToolSystem+Mode <mode>k__BackingField`  

```csharp
private Game.Tools.AreaToolSystem+Mode <mode>k__BackingField;
```

- `private Unity.Entities.Entity <recreate>k__BackingField`  

```csharp
private Unity.Entities.Entity <recreate>k__BackingField;
```

- `private System.Boolean <underground>k__BackingField`  

```csharp
private System.Boolean <underground>k__BackingField;
```

- `private System.Boolean <allowGenerate>k__BackingField`  

```csharp
private System.Boolean <allowGenerate>k__BackingField;
```

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.Input.IProxyAction m_AddAreaNode`  

```csharp
private Game.Input.IProxyAction m_AddAreaNode;
```

- `private Game.Input.IProxyAction m_InsertAreaNode`  

```csharp
private Game.Input.IProxyAction m_InsertAreaNode;
```

- `private Game.Input.IProxyAction m_MergeAreaNode`  

```csharp
private Game.Input.IProxyAction m_MergeAreaNode;
```

- `private Game.Input.IProxyAction m_MoveAreaNode`  

```csharp
private Game.Input.IProxyAction m_MoveAreaNode;
```

- `private Game.Input.IProxyAction m_DeleteAreaNode`  

```csharp
private Game.Input.IProxyAction m_DeleteAreaNode;
```

- `private Game.Input.IProxyAction m_UndoAreaNode`  

```csharp
private Game.Input.IProxyAction m_UndoAreaNode;
```

- `private Game.Input.IProxyAction m_CompleteArea`  

```csharp
private Game.Input.IProxyAction m_CompleteArea;
```

- `private Game.Input.IProxyAction m_CreateArea`  

```csharp
private Game.Input.IProxyAction m_CreateArea;
```

- `private Game.Input.IProxyAction m_DeleteArea`  

```csharp
private Game.Input.IProxyAction m_DeleteArea;
```

- `private Game.Input.IProxyAction m_DiscardInsertAreaNode`  

```csharp
private Game.Input.IProxyAction m_DiscardInsertAreaNode;
```

- `private Game.Input.IProxyAction m_DiscardMoveAreaNode`  

```csharp
private Game.Input.IProxyAction m_DiscardMoveAreaNode;
```

- `private Game.Input.IProxyAction m_DiscardMergeAreaNode`  

```csharp
private Game.Input.IProxyAction m_DiscardMergeAreaNode;
```

- `private Game.Input.IProxyAction m_CreateAreaOrMoveAreaNode`  

```csharp
private Game.Input.IProxyAction m_CreateAreaOrMoveAreaNode;
```

- `private Game.Input.IProxyAction m_CreateAreaOrInsertAreaNode`  

```csharp
private Game.Input.IProxyAction m_CreateAreaOrInsertAreaNode;
```

- `private System.Boolean m_ApplyBlocked`  

```csharp
private System.Boolean m_ApplyBlocked;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_TempAreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempAreaQuery;
```

- `private Unity.Entities.EntityQuery m_TempBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_MapTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_MapTileQuery;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Game.Tools.ControlPoint m_LastRaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_LastRaycastPoint;
```

- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  

```csharp
private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
```

- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_MoveStartPositions`  

```csharp
private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_MoveStartPositions;
```

- `private Colossal.Collections.NativeValue<Game.Tools.AreaToolSystem+Tooltip> m_Tooltip`  

```csharp
private Colossal.Collections.NativeValue<Game.Tools.AreaToolSystem+Tooltip> m_Tooltip;
```

- `private Game.Tools.AreaToolSystem+Mode m_LastMode`  

```csharp
private Game.Tools.AreaToolSystem+Mode m_LastMode;
```

- `private Game.Tools.AreaToolSystem+State m_State`  

```csharp
private Game.Tools.AreaToolSystem+State m_State;
```

- `private Game.Prefabs.AreaPrefab m_Prefab`  

```csharp
private Game.Prefabs.AreaPrefab m_Prefab;
```

- `private System.Boolean m_ControlPointsMoved`  

```csharp
private System.Boolean m_ControlPointsMoved;
```

- `private System.Boolean m_AllowCreateArea`  

```csharp
private System.Boolean m_AllowCreateArea;
```

- `private System.Boolean m_ForceCancel`  

```csharp
private System.Boolean m_ForceCancel;
```

- `private Game.Tools.AreaToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.AreaToolSystem+TypeHandle __TypeHandle;
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

- `public System.Int32 uiModeIndex { get }`  

```csharp
public System.Int32 uiModeIndex { get; }
```

- `public Game.Tools.AreaToolSystem+Mode mode { get; set }`  

```csharp
public Game.Tools.AreaToolSystem+Mode mode { get; set; }
```

- `public Game.Tools.AreaToolSystem+Mode actualMode { get }`  

```csharp
public Game.Tools.AreaToolSystem+Mode actualMode { get; }
```

- `public Unity.Entities.Entity recreate { get; set }`  

```csharp
public Unity.Entities.Entity recreate { get; set; }
```

- `public System.Boolean underground { get; set }`  

```csharp
public System.Boolean underground { get; set; }
```

- `public System.Boolean allowGenerate { get; private set }`  

```csharp
public System.Boolean allowGenerate { get; private set; }
```

- `public Game.Tools.AreaToolSystem+State state { get }`  

```csharp
public Game.Tools.AreaToolSystem+State state { get; }
```

- `public Game.Tools.AreaToolSystem+Tooltip tooltip { get }`  

```csharp
public Game.Tools.AreaToolSystem+Tooltip tooltip { get; }
```

- `public Game.Prefabs.AreaPrefab prefab { get; set }`  

```csharp
public Game.Prefabs.AreaPrefab prefab { get; set; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```


## Constructors

- `public AreaToolSystem()`  

```csharp
[Preserve]
	public AreaToolSystem()
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
			if (actualMode == Mode.Generate)
			{
				if (GetAllowApply() && !m_TempAreaQuery.IsEmptyIgnoreFilter)
				{
					NativeArray<Entity> applyTempAreas = m_TempAreaQuery.ToEntityArray(Allocator.TempJob);
					base.applyMode = ApplyMode.Apply;
					m_ControlPoints.Clear();
					if (GetRaycastResult(out var controlPoint2))
					{
						m_LastRaycastPoint = controlPoint2;
						m_ControlPoints.Add(in controlPoint2);
						m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PolygonToolDropPointSound);
						inputDeps = SnapControlPoints(inputDeps, applyTempAreas);
						inputDeps = UpdateDefinitions(inputDeps, applyTempAreas, default(NativeArray<Entity>));
					}
					if (applyTempAreas.IsCreated)
					{
						applyTempAreas.Dispose(inputDeps);
					}
					return inputDeps;
				}
				return Update(inputDeps, fullUpdate: false);
			}
			if (m_ControlPoints.Length > 0)
			{
				base.applyMode = ApplyMode.Clear;
				ControlPoint value = m_ControlPoints[0];
				if (base.EntityManager.HasComponent<Area>(value.m_OriginalEntity) && math.any(value.m_ElementIndex >= 0) && !singleFrameOnly)
				{
					m_State = State.Modify;
					m_ControlPointsMoved = false;
					m_MoveStartPositions.Clear();
					m_MoveStartPositions.AddRange(m_ControlPoints.AsArray());
					m_ControlPoints.Clear();
					if (GetRaycastResult(out var controlPoint3))
					{
						m_LastRaycastPoint = controlPoint3;
						m_ControlPoints.Add(in controlPoint3);
						m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PolygonToolSelectPointSound);
						inputDeps = SnapControlPoints(inputDeps, default(NativeArray<Entity>));
						JobHandle.ScheduleBatchedJobs();
						inputDeps.Complete();
						ControlPoint other = m_ControlPoints[0];
						if (!m_MoveStartPositions[0].Equals(other))
						{
							float minNodeDistance = AreaUtils.GetMinNodeDistance(m_PrefabSystem.GetComponentData<AreaGeometryData>(prefab));
							if (math.distance(m_MoveStartPositions[0].m_Position, other.m_Position) < minNodeDistance * 0.5f)
							{
								m_ControlPoints[0] = m_MoveStartPositions[0];
							}
							else
							{
								m_ControlPointsMoved = true;
							}
						}
						inputDeps = UpdateDefinitions(inputDeps, default(NativeArray<Entity>), default(NativeArray<Entity>));
					}
					else
					{
						m_ControlPoints.Add(in value);
					}
					return inputDeps;
				}
				if (GetAllowApply() && !value.Equals(default(ControlPoint)) && m_AllowCreateArea)
				{
					m_State = State.Create;
					m_MoveStartPositions.Clear();
					m_ControlPoints.Clear();
					m_ControlPoints.Add(in value);
					m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PolygonToolDropPointSound);
					if (GetRaycastResult(out var controlPoint4))
					{
						m_LastRaycastPoint = controlPoint4;
						m_ControlPoints.Add(in controlPoint4);
						inputDeps = SnapControlPoints(inputDeps, default(NativeArray<Entity>));
						inputDeps = UpdateDefinitions(inputDeps, default(NativeArray<Entity>), default(NativeArray<Entity>));
					}
					else
					{
						m_ControlPoints.Add(in value);
					}
					return inputDeps;
				}
				return Update(inputDeps, fullUpdate: false);
			}
			return Update(inputDeps, fullUpdate: false);
		case State.Create:
			if (!m_TempAreaQuery.IsEmptyIgnoreFilter)
			{
				if (!GetAllowApply())
				{
					m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PlaceBuildingFailSound);
				}
				else
				{
					AreaGeometryData componentData = m_PrefabSystem.GetComponentData<AreaGeometryData>(prefab);
					float num = math.distance(m_ControlPoints[m_ControlPoints.Length - 2].m_Position, m_ControlPoints[m_ControlPoints.Length - 1].m_Position);
					float minNodeDistance2 = AreaUtils.GetMinNodeDistance(componentData);
					if (num >= minNodeDistance2)
					{
						bool flag = true;
						NativeArray<Area> nativeArray = m_TempAreaQuery.ToComponentDataArray<Area>(Allocator.TempJob);
						for (int i = 0; i < nativeArray.Length; i++)
						{
							flag &= (nativeArray[i].m_Flags & AreaFlags.Complete) != 0;
						}
						nativeArray.Dispose();
						NativeArray<Entity> applyTempAreas2 = default(NativeArray<Entity>);
						if (flag)
						{
							m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PolygonToolFinishAreaSound);
							base.applyMode = ApplyMode.Apply;
							m_State = State.Default;
							m_ControlPoints.Clear();
							if (recreate != Entity.Null)
							{
								if (m_ObjectToolSystem.mode == ObjectToolSystem.Mode.Move)
								{
									m_ToolSystem.activeTool = m_DefaultToolSystem;
								}
								else
								{
									m_ToolSystem.activeTool = m_ObjectToolSystem;
								}
								return inputDeps;
							}
							applyTempAreas2 = m_TempAreaQuery.ToEntityArray(Allocator.TempJob);
						}
						else
						{
							m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PolygonToolDropPointSound);
							base.applyMode = ApplyMode.Clear;
						}
						if (GetRaycastResult(out var controlPoint5))
						{
							m_LastRaycastPoint = controlPoint5;
							m_ControlPoints.Add(in controlPoint5);
							inputDeps = SnapControlPoints(inputDeps, applyTempAreas2);
							inputDeps = UpdateDefinitions(inputDeps, applyTempAreas2, default(NativeArray<Entity>));
						}
						if (applyTempAreas2.IsCreated)
						{
							applyTempAreas2.Dispose(inputDeps);
						}
						return inputDeps;
					}
				}
			}
			return Update(inputDeps, fullUpdate: false);
		case State.Modify:
		{
			if (!m_ControlPointsMoved && GetAllowApply() && m_ControlPoints.Length > 0)
			{
				if (m_AllowCreateArea)
				{
					ControlPoint value2 = m_ControlPoints[0];
					base.applyMode = ApplyMode.Clear;
					m_State = State.Create;
					m_MoveStartPositions.Clear();
					m_ControlPoints.Clear();
					m_ControlPoints.Add(in value2);
					m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PolygonToolDropPointSound);
					if (GetRaycastResult(out var controlPoint6))
					{
						m_LastRaycastPoint = controlPoint6;
						m_ControlPoints.Add(in controlPoint6);
						inputDeps = SnapControlPoints(inputDeps, default(NativeArray<Entity>));
						inputDeps = UpdateDefinitions(inputDeps, default(NativeArray<Entity>), default(NativeArray<Entity>));
					}
					else
					{
						m_ControlPoints.Add(in value2);
					}
					return inputDeps;
				}
				base.applyMode = ApplyMode.Clear;
				m_State = State.Default;
				m_ControlPoints.Clear();
				if (GetRaycastResult(out var controlPoint7))
				{
					m_LastRaycastPoint = controlPoint7;
					m_ControlPoints.Add(in controlPoint7);
					m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PolygonToolDropPointSound);
					inputDeps = SnapControlPoints(inputDeps, default(NativeArray<Entity>));
					inputDeps = UpdateDefinitions(inputDeps, default(NativeArray<Entity>), default(NativeArray<Entity>));
				}
				return inputDeps;
			}
			NativeArray<Entity> applyTempAreas3 = default(NativeArray<Entity>);
			NativeArray<Entity> applyTempBuildings = default(NativeArray<Entity>);
			if (GetAllowApply() && !m_TempAreaQuery.IsEmptyIgnoreFilter)
			{
				base.applyMode = ApplyMode.Apply;
				applyTempAreas3 = m_TempAreaQuery.ToEntityArray(Allocator.TempJob);
				applyTempBuildings = m_TempBuildingQuery.ToEntityArray(Allocator.TempJob);
			}
			else
			{
				base.applyMode = ApplyMode.Clear;
			}
			m_State = State.Default;
			m_ControlPoints.Clear();
			if (GetRaycastResult(out var controlPoint8))
			{
				m_LastRaycastPoint = controlPoint8;
				m_ControlPoints.Add(in controlPoint8);
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PolygonToolDropPointSound);
				inputDeps = SnapControlPoints(inputDeps, applyTempAreas3);
				inputDeps = UpdateDefinitions(inputDeps, applyTempAreas3, applyTempBuildings);
			}
			if (applyTempAreas3.IsCreated)
			{
				applyTempAreas3.Dispose(inputDeps);
			}
			if (applyTempBuildings.IsCreated)
			{
				applyTempBuildings.Dispose(inputDeps);
			}
			return inputDeps;
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
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PolygonToolRemovePointSound);
				inputDeps = SnapControlPoints(inputDeps, default(NativeArray<Entity>));
				inputDeps = UpdateDefinitions(inputDeps, default(NativeArray<Entity>), default(NativeArray<Entity>));
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
		switch (m_State)
		{
		case State.Default:
			if (actualMode == Mode.Generate)
			{
				return Update(inputDeps, fullUpdate: false);
			}
			if (GetAllowApply() && m_ControlPoints.Length > 0)
			{
				base.applyMode = ApplyMode.Clear;
				ControlPoint value = m_ControlPoints[0];
				if (base.EntityManager.HasComponent<Area>(value.m_OriginalEntity) && value.m_ElementIndex.x >= 0)
				{
					if (base.EntityManager.TryGetBuffer(value.m_OriginalEntity, isReadOnly: true, out DynamicBuffer<Game.Areas.Node> buffer) && buffer.Length <= 3)
					{
						m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PolygonToolDeleteAreaSound);
					}
					else
					{
						m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PolygonToolRemovePointSound);
					}
					m_State = State.Remove;
					m_ControlPointsMoved = false;
					m_ForceCancel = singleFrameOnly;
					m_MoveStartPositions.Clear();
					m_MoveStartPositions.AddRange(m_ControlPoints.AsArray());
					m_ControlPoints.Clear();
					if (GetRaycastResult(out var controlPoint2))
					{
						m_LastRaycastPoint = controlPoint2;
						m_ControlPoints.Add(in controlPoint2);
						inputDeps = SnapControlPoints(inputDeps, default(NativeArray<Entity>));
						inputDeps = UpdateDefinitions(inputDeps, default(NativeArray<Entity>), default(NativeArray<Entity>));
					}
					else
					{
						m_ControlPoints.Add(in value);
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
			if (recreate != Entity.Null && m_ControlPoints.Length <= 2)
			{
				m_ToolSystem.activeTool = m_ObjectToolSystem;
				return inputDeps;
			}
			m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PolygonToolRemovePointSound);
			if (GetRaycastResult(out var controlPoint4))
			{
				m_LastRaycastPoint = controlPoint4;
				m_ControlPoints[m_ControlPoints.Length - 1] = controlPoint4;
				inputDeps = SnapControlPoints(inputDeps, default(NativeArray<Entity>));
				inputDeps = UpdateDefinitions(inputDeps, default(NativeArray<Entity>), default(NativeArray<Entity>));
			}
			else if (m_ControlPoints.Length >= 2)
			{
				m_ControlPoints[m_ControlPoints.Length - 1] = m_ControlPoints[m_ControlPoints.Length - 2];
				inputDeps = UpdateDefinitions(inputDeps, default(NativeArray<Entity>), default(NativeArray<Entity>));
			}
			return inputDeps;
		}
		case State.Modify:
		{
			m_ControlPoints.Clear();
			base.applyMode = ApplyMode.Clear;
			m_State = State.Default;
			if (GetRaycastResult(out var controlPoint3))
			{
				m_LastRaycastPoint = controlPoint3;
				m_ControlPoints.Add(in controlPoint3);
				inputDeps = SnapControlPoints(inputDeps, default(NativeArray<Entity>));
				inputDeps = UpdateDefinitions(inputDeps, default(NativeArray<Entity>), default(NativeArray<Entity>));
			}
			return inputDeps;
		}
		case State.Remove:
		{
			NativeArray<Entity> applyTempAreas = default(NativeArray<Entity>);
			NativeArray<Entity> applyTempBuildings = default(NativeArray<Entity>);
			if (GetAllowApply() && !m_TempAreaQuery.IsEmptyIgnoreFilter)
			{
				base.applyMode = ApplyMode.Apply;
				applyTempAreas = m_TempAreaQuery.ToEntityArray(Allocator.TempJob);
				applyTempBuildings = m_TempBuildingQuery.ToEntityArray(Allocator.TempJob);
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
				inputDeps = SnapControlPoints(inputDeps, applyTempAreas);
				inputDeps = UpdateDefinitions(inputDeps, applyTempAreas, applyTempBuildings);
			}
			if (applyTempAreas.IsCreated)
			{
				applyTempAreas.Dispose(inputDeps);
			}
			if (applyTempBuildings.IsCreated)
			{
				applyTempBuildings.Dispose(inputDeps);
			}
			return inputDeps;
		}
		default:
			return Update(inputDeps, fullUpdate: false);
		}
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

- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
private static void GetAvailableSnapMask(AreaGeometryData prefabAreaData, bool editorMode, out Snap onMask, out Snap offMask)
	{
		onMask = Snap.ExistingGeometry | Snap.StraightDirection;
		offMask = onMask;
		switch (prefabAreaData.m_Type)
		{
		case Game.Areas.AreaType.Lot:
			onMask |= Snap.NetSide | Snap.ObjectSide;
			offMask |= Snap.NetSide | Snap.ObjectSide;
			if (editorMode)
			{
				onMask |= Snap.LotGrid | Snap.AutoParent;
				offMask |= Snap.LotGrid | Snap.AutoParent;
			}
			break;
		case Game.Areas.AreaType.District:
			onMask |= Snap.NetMiddle;
			offMask |= Snap.NetMiddle;
			break;
		case Game.Areas.AreaType.Space:
			onMask |= Snap.NetSide | Snap.ObjectSide | Snap.ObjectSurface;
			offMask |= Snap.NetSide | Snap.ObjectSide | Snap.ObjectSurface;
			if (editorMode)
			{
				onMask |= Snap.LotGrid | Snap.AutoParent;
				offMask |= Snap.LotGrid | Snap.AutoParent;
			}
			break;
		case Game.Areas.AreaType.Surface:
			onMask |= Snap.NetSide | Snap.ObjectSide;
			offMask |= Snap.NetSide | Snap.ObjectSide;
			if (editorMode)
			{
				onMask |= Snap.LotGrid | Snap.AutoParent;
				offMask |= Snap.LotGrid | Snap.AutoParent;
			}
			break;
		case Game.Areas.AreaType.MapTile:
			break;
		}
	}
```

- `private static GetAvailableSnapMask(Game.Prefabs.AreaGeometryData prefabAreaData, System.Boolean editorMode, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
private static void GetAvailableSnapMask(AreaGeometryData prefabAreaData, bool editorMode, out Snap onMask, out Snap offMask)
	{
		onMask = Snap.ExistingGeometry | Snap.StraightDirection;
		offMask = onMask;
		switch (prefabAreaData.m_Type)
		{
		case Game.Areas.AreaType.Lot:
			onMask |= Snap.NetSide | Snap.ObjectSide;
			offMask |= Snap.NetSide | Snap.ObjectSide;
			if (editorMode)
			{
				onMask |= Snap.LotGrid | Snap.AutoParent;
				offMask |= Snap.LotGrid | Snap.AutoParent;
			}
			break;
		case Game.Areas.AreaType.District:
			onMask |= Snap.NetMiddle;
			offMask |= Snap.NetMiddle;
			break;
		case Game.Areas.AreaType.Space:
			onMask |= Snap.NetSide | Snap.ObjectSide | Snap.ObjectSurface;
			offMask |= Snap.NetSide | Snap.ObjectSide | Snap.ObjectSurface;
			if (editorMode)
			{
				onMask |= Snap.LotGrid | Snap.AutoParent;
				offMask |= Snap.LotGrid | Snap.AutoParent;
			}
			break;
		case Game.Areas.AreaType.Surface:
			onMask |= Snap.NetSide | Snap.ObjectSide;
			offMask |= Snap.NetSide | Snap.ObjectSide;
			if (editorMode)
			{
				onMask |= Snap.LotGrid | Snap.AutoParent;
				offMask |= Snap.LotGrid | Snap.AutoParent;
			}
			break;
		case Game.Areas.AreaType.MapTile:
			break;
		}
	}
```

- `public GetControlPoints(Unity.Collections.NativeList`1[[Game.Tools.ControlPoint, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& moveStartPositions, Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.ControlPoint>`  

```csharp
public NativeList<ControlPoint> GetControlPoints(out NativeList<ControlPoint> moveStartPositions, out JobHandle dependencies)
	{
		moveStartPositions = m_MoveStartPositions;
		dependencies = base.Dependency;
		return m_ControlPoints;
	}
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public override PrefabBase GetPrefab()
	{
		return prefab;
	}
```

- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  

```csharp
public override void GetUIModes(List<ToolMode> modes)
	{
		modes.Add(new ToolMode(Mode.Edit.ToString(), 0));
		if (allowGenerate)
		{
			modes.Add(new ToolMode(Mode.Generate.ToString(), 1));
		}
	}
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public override void InitializeRaycast()
	{
		base.InitializeRaycast();
		if (prefab != null)
		{
			AreaGeometryData componentData = m_PrefabSystem.GetComponentData<AreaGeometryData>(prefab);
			GetAvailableSnapMask(out var onMask, out var offMask);
			Snap actualSnap = ToolBaseSystem.GetActualSnap(selectedSnap, onMask, offMask);
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.SubElements;
			m_ToolRaycastSystem.typeMask = TypeMask.Terrain | TypeMask.Areas;
			m_ToolRaycastSystem.areaTypeMask = AreaUtils.GetTypeMask(componentData.m_Type);
			if ((componentData.m_Flags & Game.Areas.GeometryFlags.OnWaterSurface) != 0)
			{
				m_ToolRaycastSystem.typeMask |= TypeMask.Water;
			}
			if ((actualSnap & Snap.ObjectSurface) != Snap.None)
			{
				m_ToolRaycastSystem.typeMask |= TypeMask.StaticObjects;
				if (m_ToolSystem.actionMode.IsEditor())
				{
					m_ToolRaycastSystem.raycastFlags |= RaycastFlags.Placeholders;
				}
				if (underground)
				{
					m_ToolRaycastSystem.collisionMask = CollisionMask.Underground;
					m_ToolRaycastSystem.typeMask &= ~(TypeMask.Terrain | TypeMask.Water);
					m_ToolRaycastSystem.raycastFlags |= RaycastFlags.PartialSurface;
				}
			}
			if ((actualSnap & Snap.ExistingGeometry) == 0 && m_State != State.Default)
			{
				m_ToolRaycastSystem.typeMask &= ~TypeMask.Areas;
			}
		}
		else
		{
			m_ToolRaycastSystem.typeMask = TypeMask.Terrain | TypeMask.Areas;
			m_ToolRaycastSystem.areaTypeMask = AreaTypeMask.None;
		}
		if (m_ToolSystem.actionMode.IsEditor())
		{
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.UpgradeIsMain;
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ObjectToolSystem = base.World.GetOrCreateSystemManaged<ObjectToolSystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_ToolOutputBarrier = base.World.GetOrCreateSystemManaged<ToolOutputBarrier>();
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_DefinitionQuery = GetDefinitionQuery();
		m_TempAreaQuery = GetEntityQuery(ComponentType.ReadOnly<Area>(), ComponentType.ReadOnly<Temp>());
		m_TempBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Temp>());
		m_MapTileQuery = GetEntityQuery(ComponentType.ReadOnly<MapTile>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_SoundQuery = GetEntityQuery(ComponentType.ReadOnly<ToolUXSoundSettingsData>());
		m_AddAreaNode = InputManager.instance.toolActionCollection.GetActionState("Add Area Node", "AreaToolSystem");
		m_InsertAreaNode = InputManager.instance.toolActionCollection.GetActionState("Insert Area Node", "AreaToolSystem");
		m_MergeAreaNode = InputManager.instance.toolActionCollection.GetActionState("Merge Area Node", "AreaToolSystem");
		m_MoveAreaNode = InputManager.instance.toolActionCollection.GetActionState("Move Area Node", "AreaToolSystem");
		m_DeleteAreaNode = InputManager.instance.toolActionCollection.GetActionState("Delete Area Node", "AreaToolSystem");
		m_UndoAreaNode = InputManager.instance.toolActionCollection.GetActionState("Undo Area Node", "AreaToolSystem");
		m_CompleteArea = InputManager.instance.toolActionCollection.GetActionState("Complete Area", "AreaToolSystem");
		m_CreateArea = InputManager.instance.toolActionCollection.GetActionState("Create Area", "AreaToolSystem");
		m_DeleteArea = InputManager.instance.toolActionCollection.GetActionState("Delete Area", "AreaToolSystem");
		m_DiscardInsertAreaNode = InputManager.instance.toolActionCollection.GetActionState("Discard Insert Area Node", "AreaToolSystem");
		m_DiscardMoveAreaNode = InputManager.instance.toolActionCollection.GetActionState("Discard Move Area Node", "AreaToolSystem");
		m_DiscardMergeAreaNode = InputManager.instance.toolActionCollection.GetActionState("Discard Merge Area Node", "AreaToolSystem");
		m_CreateAreaOrMoveAreaNode = InputManager.instance.toolActionCollection.GetActionState("Create Area Or Move Area Node", "AreaToolSystem");
		m_CreateAreaOrInsertAreaNode = InputManager.instance.toolActionCollection.GetActionState("Create Area Or Insert Area Node", "AreaToolSystem");
		selectedSnap &= ~Snap.AutoParent;
		m_ControlPoints = new NativeList<ControlPoint>(20, Allocator.Persistent);
		m_MoveStartPositions = new NativeList<ControlPoint>(10, Allocator.Persistent);
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
		m_MoveStartPositions.Dispose();
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
		m_MoveStartPositions.Clear();
		m_LastRaycastPoint = default(ControlPoint);
		m_LastMode = actualMode;
		m_State = State.Default;
		m_Tooltip.value = Tooltip.None;
		m_AllowCreateArea = false;
		m_ForceCancel = false;
		m_ApplyBlocked = false;
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		recreate = Entity.Null;
		base.OnStopRunning();
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		if (m_FocusChanged)
		{
			return inputDeps;
		}
		if (actualMode != m_LastMode)
		{
			m_ControlPoints.Clear();
			m_MoveStartPositions.Clear();
			m_LastRaycastPoint = default(ControlPoint);
			m_LastMode = actualMode;
			m_State = State.Default;
			m_Tooltip.value = Tooltip.None;
			m_AllowCreateArea = false;
		}
		bool flag = m_ForceCancel;
		m_ForceCancel = false;
		if (base.EntityManager.TryGetBuffer(recreate, isReadOnly: true, out DynamicBuffer<Game.Areas.Node> buffer))
		{
			m_State = State.Create;
			if (m_ControlPoints.Length < 3 && buffer.Length >= 2)
			{
				ref NativeList<ControlPoint> reference = ref m_ControlPoints;
				ControlPoint value = new ControlPoint
				{
					m_OriginalEntity = recreate,
					m_ElementIndex = new int2(0, -1),
					m_Position = buffer[0].m_Position,
					m_HitPosition = buffer[0].m_Position
				};
				reference.Add(in value);
				ref NativeList<ControlPoint> reference2 = ref m_ControlPoints;
				value = new ControlPoint
				{
					m_OriginalEntity = recreate,
					m_ElementIndex = new int2(1, -1),
					m_Position = buffer[1].m_Position,
					m_HitPosition = buffer[1].m_Position
				};
				reference2.Add(in value);
				ref NativeList<ControlPoint> reference3 = ref m_ControlPoints;
				value = new ControlPoint
				{
					m_ElementIndex = new int2(-1, -1),
					m_Position = math.lerp(buffer[0].m_Position, buffer[1].m_Position, 0.5f),
					m_HitPosition = math.lerp(buffer[0].m_Position, buffer[1].m_Position, 0.5f)
				};
				reference3.Add(in value);
			}
		}
		UpdateActions();
		if (prefab != null)
		{
			AreaGeometryData componentData = m_PrefabSystem.GetComponentData<AreaGeometryData>(prefab);
			base.requireAreas = AreaUtils.GetTypeMask(componentData.m_Type);
			base.requireZones = componentData.m_Type == Game.Areas.AreaType.Lot;
			base.requireNet = Layer.None;
			if ((componentData.m_Flags & Game.Areas.GeometryFlags.PhysicalGeometry) != 0 && (componentData.m_Flags & Game.Areas.GeometryFlags.OnWaterSurface) != 0)
			{
				base.requireNet |= Layer.Waterway;
			}
			m_AllowCreateArea = (m_ToolSystem.actionMode.IsEditor() || componentData.m_Type != Game.Areas.AreaType.Lot) && (componentData.m_Type != Game.Areas.AreaType.Surface || (componentData.m_Flags & Game.Areas.GeometryFlags.ClipTerrain) != 0 || m_PrefabSystem.HasComponent<RenderedAreaData>(prefab));
			Entity entity = Entity.Null;
			if (base.EntityManager.TryGetComponent<Owner>(recreate, out var component) && base.EntityManager.TryGetComponent<PrefabRef>(component.m_Owner, out var component2))
			{
				entity = component2.m_Prefab;
			}
			else if (!m_ToolSystem.actionMode.IsEditor())
			{
				entity = m_PrefabSystem.GetEntity(prefab);
			}
			UpdateInfoview(entity);
			GetAvailableSnapMask(componentData, m_ToolSystem.actionMode.IsEditor(), out m_SnapOnMask, out m_SnapOffMask);
			allowUnderground = (ToolBaseSystem.GetActualSnap(selectedSnap, m_SnapOnMask, m_SnapOffMask) & Snap.ObjectSurface) != 0;
			base.requireUnderground = allowUnderground && underground;
			if (m_State != State.Default && base.actionsEnabled && !base.applyAction.enabled)
			{
				m_State = State.Default;
				return Clear(inputDeps);
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
					if (base.applyAction.WasReleasedThisFrame())
					{
						return Apply(inputDeps);
					}
					break;
				case State.Remove:
					if (flag || base.cancelAction.WasPressedThisFrame())
					{
						m_ApplyBlocked = true;
						m_State = State.Default;
						return Update(inputDeps, fullUpdate: true);
					}
					if (base.secondaryApplyAction.WasReleasedThisFrame())
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
			base.requireAreas = AreaTypeMask.None;
			base.requireZones = false;
			base.requireNet = Layer.None;
			base.requireUnderground = false;
			m_AllowCreateArea = false;
			allowUnderground = false;
			UpdateInfoview(Entity.Null);
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

- `private SnapControlPoints(Unity.Jobs.JobHandle inputDeps, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempAreas) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle SnapControlPoints(JobHandle inputDeps, NativeArray<Entity> applyTempAreas)
	{
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle dependencies3;
		SnapJob jobData = new SnapJob
		{
			m_AllowCreateArea = m_AllowCreateArea,
			m_ControlPointsMoved = m_ControlPointsMoved,
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_Snap = GetActualSnap(),
			m_State = m_State,
			m_Prefab = m_PrefabSystem.GetEntity(prefab),
			m_ApplyTempAreas = applyTempAreas,
			m_MoveStartPositions = m_MoveStartPositions,
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StartGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EndGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingExtensionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingExtensionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AssetStampData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AssetStampData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Lot_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
			m_CachedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Tools_LocalNodeCache_RO_BufferLookup, ref base.CheckedStateRef),
			m_Triangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_AreaSearchTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies),
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies2),
			m_ObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies3),
			m_ControlPoints = m_ControlPoints
		};
		inputDeps = JobHandle.CombineDependencies(inputDeps, JobHandle.CombineDependencies(dependencies, dependencies2, dependencies3));
		JobHandle jobHandle = IJobExtensions.Schedule(jobData, inputDeps);
		m_AreaSearchSystem.AddSearchTreeReader(jobHandle);
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle);
		return jobHandle;
	}
```

- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public override bool TrySetPrefab(PrefabBase prefab)
	{
		if (prefab is AreaPrefab areaPrefab)
		{
			this.prefab = areaPrefab;
			return true;
		}
		return false;
	}
```

- `private Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Update(JobHandle inputDeps, bool fullUpdate)
	{
		if (GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate))
		{
			forceUpdate = forceUpdate || fullUpdate;
			if (m_ControlPoints.Length == 0)
			{
				m_LastRaycastPoint = controlPoint;
				m_ControlPoints.Add(in controlPoint);
				inputDeps = SnapControlPoints(inputDeps, default(NativeArray<Entity>));
				base.applyMode = ApplyMode.Clear;
				return UpdateDefinitions(inputDeps, default(NativeArray<Entity>), default(NativeArray<Entity>));
			}
			if (m_LastRaycastPoint.Equals(controlPoint) && !forceUpdate)
			{
				base.applyMode = ApplyMode.None;
				return inputDeps;
			}
			m_LastRaycastPoint = controlPoint;
			int index = math.select(0, m_ControlPoints.Length - 1, m_State == State.Create);
			ControlPoint value = m_ControlPoints[index];
			m_ControlPoints[index] = controlPoint;
			inputDeps = SnapControlPoints(inputDeps, default(NativeArray<Entity>));
			JobHandle.ScheduleBatchedJobs();
			inputDeps.Complete();
			ControlPoint other = m_ControlPoints[index];
			if (value.EqualsIgnoreHit(other))
			{
				base.applyMode = ApplyMode.None;
			}
			else
			{
				float minNodeDistance = AreaUtils.GetMinNodeDistance(m_PrefabSystem.GetComponentData<AreaGeometryData>(prefab));
				if (m_State == State.Modify && !m_ControlPointsMoved && math.distance(value.m_Position, other.m_Position) < minNodeDistance * 0.5f)
				{
					m_ControlPoints[index] = value;
					base.applyMode = ApplyMode.None;
				}
				else
				{
					m_ControlPointsMoved = true;
					base.applyMode = ApplyMode.Clear;
					inputDeps = UpdateDefinitions(inputDeps, default(NativeArray<Entity>), default(NativeArray<Entity>));
				}
			}
			return inputDeps;
		}
		if (m_LastRaycastPoint.Equals(controlPoint))
		{
			if (forceUpdate || fullUpdate)
			{
				base.applyMode = ApplyMode.Clear;
				return UpdateDefinitions(inputDeps, default(NativeArray<Entity>), default(NativeArray<Entity>));
			}
			base.applyMode = ApplyMode.None;
			return inputDeps;
		}
		m_LastRaycastPoint = controlPoint;
		if (m_State == State.Default && m_ControlPoints.Length >= 1)
		{
			base.applyMode = ApplyMode.Clear;
			m_ControlPoints.Clear();
			m_ControlPoints.Add(default(ControlPoint));
			return UpdateDefinitions(inputDeps, default(NativeArray<Entity>), default(NativeArray<Entity>));
		}
		if (m_State == State.Modify && m_ControlPoints.Length >= 1)
		{
			m_ControlPointsMoved = true;
			base.applyMode = ApplyMode.Clear;
			m_ControlPoints[0] = m_MoveStartPositions[0];
			return UpdateDefinitions(inputDeps, default(NativeArray<Entity>), default(NativeArray<Entity>));
		}
		if (m_State == State.Remove && m_ControlPoints.Length >= 1)
		{
			m_ControlPointsMoved = true;
			base.applyMode = ApplyMode.Clear;
			m_ControlPoints[0] = m_MoveStartPositions[0];
			return UpdateDefinitions(inputDeps, default(NativeArray<Entity>), default(NativeArray<Entity>));
		}
		if (m_ControlPoints.Length >= 2)
		{
			m_ControlPointsMoved = true;
			base.applyMode = ApplyMode.Clear;
			m_ControlPoints[m_ControlPoints.Length - 1] = m_ControlPoints[m_ControlPoints.Length - 2];
			return UpdateDefinitions(inputDeps, default(NativeArray<Entity>), default(NativeArray<Entity>));
		}
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
			if (m_ControlPoints.Length < 1 || m_ControlPoints[0].Equals(default(ControlPoint)))
			{
				base.applyAction.enabled = base.actionsEnabled;
				base.applyActionOverride = null;
				break;
			}
			for (int k = 0; k < m_ControlPoints.Length; k++)
			{
				if (!base.EntityManager.TryGetComponent<Area>(m_ControlPoints[k].m_OriginalEntity, out var component2) || (component2.m_Flags & AreaFlags.Complete) == 0 || !base.EntityManager.TryGetBuffer(m_ControlPoints[k].m_OriginalEntity, isReadOnly: true, out DynamicBuffer<Game.Areas.Node> buffer2))
				{
					continue;
				}
				for (int l = 0; l < buffer2.Length; l++)
				{
					if (buffer2[l].m_Position.Equals(m_ControlPoints[k].m_Position))
					{
						base.applyAction.enabled = base.actionsEnabled;
						base.applyActionOverride = (base.EntityManager.HasComponent<Game.Areas.Lot>(m_ControlPoints[k].m_OriginalEntity) ? m_MoveAreaNode : m_CreateAreaOrMoveAreaNode);
						return;
					}
				}
				base.applyAction.enabled = base.actionsEnabled;
				base.applyActionOverride = (base.EntityManager.HasComponent<Game.Areas.Lot>(m_ControlPoints[k].m_OriginalEntity) ? m_InsertAreaNode : m_CreateAreaOrInsertAreaNode);
				return;
			}
			if (!base.EntityManager.HasComponent<Game.Areas.Node>(m_ControlPoints[0].m_OriginalEntity) || !math.any(m_ControlPoints[0].m_ElementIndex >= 0))
			{
				base.applyAction.enabled = base.actionsEnabled;
				base.applyActionOverride = m_CreateArea;
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
					base.applyActionOverride = (GetAllowApply() ? m_AddAreaNode : null);
					break;
				}
			}
			if (m_ControlPoints.Length >= 3)
			{
				ref NativeList<ControlPoint> reference5 = ref m_ControlPoints;
				if (reference5[reference5.Length - 1].m_Position.Equals(m_ControlPoints[0].m_Position))
				{
					base.applyAction.enabled = base.actionsEnabled;
					base.applyActionOverride = (GetAllowApply() ? m_CompleteArea : null);
					break;
				}
			}
			base.applyAction.enabled = base.actionsEnabled;
			base.applyActionOverride = null;
			break;
		}
		case State.Modify:
		{
			for (int i = 0; i < m_MoveStartPositions.Length; i++)
			{
				if (!base.EntityManager.TryGetComponent<Area>(m_MoveStartPositions[i].m_OriginalEntity, out var component) || (component.m_Flags & AreaFlags.Complete) == 0 || !base.EntityManager.TryGetBuffer(m_MoveStartPositions[i].m_OriginalEntity, isReadOnly: true, out DynamicBuffer<Game.Areas.Node> buffer))
				{
					continue;
				}
				for (int j = 0; j < buffer.Length; j++)
				{
					if (!buffer[j].m_Position.Equals(m_MoveStartPositions[i].m_Position) && buffer[j].m_Position.Equals(m_ControlPoints[0].m_Position))
					{
						base.applyAction.enabled = base.actionsEnabled;
						base.applyActionOverride = m_MergeAreaNode;
						return;
					}
					if (buffer[j].m_Position.Equals(m_MoveStartPositions[i].m_Position))
					{
						base.applyAction.enabled = base.actionsEnabled;
						base.applyActionOverride = m_MoveAreaNode;
						return;
					}
				}
				base.applyAction.enabled = base.actionsEnabled;
				base.applyActionOverride = m_InsertAreaNode;
				return;
			}
			base.applyAction.enabled = false;
			base.applyActionOverride = null;
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
			for (int i = 0; i < m_MoveStartPositions.Length; i++)
			{
				if (!base.EntityManager.TryGetComponent<Area>(m_MoveStartPositions[i].m_OriginalEntity, out var component) || (component.m_Flags & AreaFlags.Complete) == 0 || !base.EntityManager.TryGetBuffer(m_MoveStartPositions[i].m_OriginalEntity, isReadOnly: true, out DynamicBuffer<Game.Areas.Node> buffer))
				{
					continue;
				}
				for (int j = 0; j < buffer.Length; j++)
				{
					if (!buffer[j].m_Position.Equals(m_MoveStartPositions[i].m_Position) && buffer[j].m_Position.Equals(m_ControlPoints[0].m_Position))
					{
						base.cancelAction.enabled = base.actionsEnabled;
						base.cancelActionOverride = m_DiscardMergeAreaNode;
						return;
					}
					if (buffer[j].m_Position.Equals(m_MoveStartPositions[i].m_Position))
					{
						base.cancelAction.enabled = base.actionsEnabled;
						base.cancelActionOverride = m_DiscardMoveAreaNode;
						return;
					}
				}
				base.cancelAction.enabled = base.actionsEnabled;
				base.cancelActionOverride = m_DiscardInsertAreaNode;
				return;
			}
			base.cancelAction.enabled = false;
			base.cancelActionOverride = null;
		}
		else
		{
			base.cancelAction.enabled = false;
			base.cancelActionOverride = null;
		}
	}
```

- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempAreas, Unity.Collections.NativeArray<Unity.Entities.Entity> applyTempBuildings) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateDefinitions(JobHandle inputDeps, NativeArray<Entity> applyTempAreas, NativeArray<Entity> applyTempBuildings)
	{
		JobHandle jobHandle = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
		if (prefab != null)
		{
			if (mode == Mode.Generate)
			{
				JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(new RemoveMapTilesJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_NodeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Node_RO_BufferTypeHandle, ref base.CheckedStateRef),
					m_CacheType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Tools_LocalNodeCache_RO_BufferTypeHandle, ref base.CheckedStateRef),
					m_ControlPoints = m_ControlPoints,
					m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer().AsParallelWriter()
				}, m_MapTileQuery, inputDeps);
				m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle2);
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
			}
			JobHandle jobHandle3 = IJobExtensions.Schedule(new CreateDefinitionsJob
			{
				m_AllowCreateArea = m_AllowCreateArea,
				m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
				m_Mode = actualMode,
				m_State = m_State,
				m_Prefab = m_PrefabSystem.GetEntity(prefab),
				m_Recreate = recreate,
				m_ApplyTempAreas = applyTempAreas,
				m_ApplyTempBuildings = applyTempBuildings,
				m_MoveStartPositions = m_MoveStartPositions,
				m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ClearData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Clear_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpaceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Space_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Area_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NetElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EditorContainerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LocalTransformCacheData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_LocalTransformCache_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
				m_Triangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
				m_CachedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Tools_LocalNodeCache_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
				m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
				m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
				m_ControlPoints = m_ControlPoints,
				m_Tooltip = m_Tooltip,
				m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer()
			}, inputDeps);
			m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle3);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle3);
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
			if (m_ControlPoints.Length == 1 && base.EntityManager.TryGetComponent<Area>(m_ControlPoints[0].m_OriginalEntity, out var component) && (component.m_Flags & AreaFlags.Complete) != 0 && base.EntityManager.TryGetBuffer(m_ControlPoints[0].m_OriginalEntity, isReadOnly: true, out DynamicBuffer<Game.Areas.Node> buffer))
			{
				for (int i = 0; i < buffer.Length; i++)
				{
					if (buffer[i].m_Position.Equals(m_ControlPoints[0].m_Position))
					{
						if (buffer.Length > 3)
						{
							base.secondaryApplyAction.enabled = base.actionsEnabled;
							base.secondaryApplyActionOverride = m_DeleteAreaNode;
						}
						else if (!base.EntityManager.HasComponent<Owner>(m_ControlPoints[0].m_OriginalEntity))
						{
							base.secondaryApplyAction.enabled = base.actionsEnabled;
							base.secondaryApplyActionOverride = m_DeleteArea;
						}
						else
						{
							base.secondaryApplyAction.enabled = false;
							base.secondaryApplyActionOverride = null;
						}
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
				base.secondaryApplyActionOverride = m_UndoAreaNode;
			}
			else
			{
				base.secondaryApplyAction.enabled = base.actionsEnabled;
				base.secondaryApplyActionOverride = null;
			}
			break;
		case State.Remove:
			base.secondaryApplyAction.enabled = base.actionsEnabled;
			base.secondaryApplyActionOverride = m_DeleteAreaNode;
			break;
		default:
			base.secondaryApplyAction.enabled = false;
			base.secondaryApplyActionOverride = null;
			break;
		}
	}
```


## Nested types

- `Game.Tools.AreaToolSystem+Mode`  
- `Game.Tools.AreaToolSystem+State`  
- `Game.Tools.AreaToolSystem+Tooltip`  
- `Game.Tools.AreaToolSystem+SnapJob`  
- `Game.Tools.AreaToolSystem+RemoveMapTilesJob`  
- `Game.Tools.AreaToolSystem+CreateDefinitionsJob`  
- `Game.Tools.AreaToolSystem+TypeHandle`  
- `Game.Tools.AreaToolSystem+<get_toolActions>d__56`  

