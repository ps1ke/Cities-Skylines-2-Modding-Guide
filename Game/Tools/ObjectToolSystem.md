# Game.Tools.ObjectToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ObjectToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ObjectToolSystem : Game.Tools.ObjectToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private Game.Tools.ObjectToolSystem+Mode <mode>k__BackingField;
    private Game.Tools.AgeMask <ageMask>k__BackingField;
    private Game.Tools.Snap m_SelectedSnap;
    private System.Single m_Distance;
    private System.Single <distanceScale>k__BackingField;
    private System.Boolean <underground>k__BackingField;
    private System.Boolean <allowCreate>k__BackingField;
    private System.Boolean <allowLine>k__BackingField;
    private System.Boolean <allowCurve>k__BackingField;
    private System.Boolean <allowBrush>k__BackingField;
    private System.Boolean <allowStamp>k__BackingField;
    private System.Boolean <allowAge>k__BackingField;
    private System.Boolean <allowRotation>k__BackingField;
    private Game.Tools.AreaToolSystem m_AreaToolSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Zones.SearchSystem m_ZoneSearchSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Audio.AudioManager m_AudioManager;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_ContainerQuery;
    private Unity.Entities.EntityQuery m_BrushQuery;
    private Unity.Entities.EntityQuery m_LotQuery;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_VisibleQuery;
    private Game.Input.IProxyAction m_EraseObject;
    private Game.Input.IProxyAction m_MoveObject;
    private Game.Input.IProxyAction m_PaintObject;
    private Game.Input.IProxyAction m_PlaceObject;
    private Game.Input.IProxyAction m_PlaceUpgrade;
    private Game.Input.IProxyAction m_PreciseRotation;
    private Game.Input.IProxyAction m_RotateObject;
    private Game.Input.IProxyAction m_PlaceNetEdge;
    private Game.Input.IProxyAction m_PlaceNetControlPoint;
    private Game.Input.IProxyAction m_UndoNetControlPoint;
    private Game.Input.IProxyAction m_DowngradeNetEdge;
    private Game.Input.IProxyAction m_UpgradeNetEdge;
    private Game.Input.IProxyAction m_DiscardUpgrade;
    private Game.Input.IProxyAction m_DiscardDowngrade;
    private Game.Input.IProxyAction m_ReplaceNetEdge;
    private System.Boolean m_ApplyBlocked;
    private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
    private Unity.Collections.NativeList<Game.Tools.SubSnapPoint> m_SubSnapPoints;
    private Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> m_UpgradeStates;
    private Unity.Collections.NativeReference<Game.Tools.ObjectToolSystem+Rotation> m_Rotation;
    private Unity.Collections.NativeReference<Game.Tools.NetToolSystem+AppliedUpgrade> m_AppliedUpgrade;
    private Game.Tools.ControlPoint m_LastRaycastPoint;
    private Game.Tools.ControlPoint m_StartPoint;
    private Unity.Entities.Entity m_UpgradingObject;
    private Unity.Entities.Entity m_MovingObject;
    private Unity.Entities.Entity m_MovingInitialized;
    private Game.Tools.ObjectToolSystem+State m_State;
    private Game.Tools.ObjectToolSystem+Mode m_LastActualMode;
    private System.Boolean m_RotationModified;
    private System.Boolean m_ForceCancel;
    private Unity.Mathematics.float3 m_RotationStartPosition;
    private Unity.Mathematics.quaternion m_StartRotation;
    private System.Single m_StartCameraAngle;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Game.Common.RandomSeed m_RandomSeed;
    private Game.Prefabs.ObjectPrefab m_Prefab;
    private Game.Prefabs.ObjectPrefab m_SelectedPrefab;
    private Game.Prefabs.TransformPrefab m_TransformPrefab;
    private Game.CameraController m_CameraController;
    private Game.Tools.ObjectToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;
    private static const System.String kTree;

    public System.String toolID { get; }
    public System.Int32 uiModeIndex { get; }
    public Game.Tools.ObjectToolSystem+Mode mode { get; set; }
    public Game.Tools.ObjectToolSystem+Mode actualMode { get; }
    public System.Boolean isUpgradeMode { get; }
    public Game.Tools.AgeMask ageMask { get; set; }
    public Game.Tools.AgeMask actualAgeMask { get; }
    public Game.Prefabs.ObjectPrefab prefab { get; set; }
    public Game.Prefabs.TransformPrefab transform { get; set; }
    public Game.Tools.Snap selectedSnap { get; set; }
    public System.Single distance { get; set; }
    public System.Single distanceScale { get; private set; }
    public System.Boolean underground { get; set; }
    public System.Boolean allowCreate { get; private set; }
    public System.Boolean allowLine { get; private set; }
    public System.Boolean allowCurve { get; private set; }
    public System.Boolean allowBrush { get; private set; }
    public System.Boolean allowStamp { get; private set; }
    public System.Boolean allowAge { get; private set; }
    public System.Boolean allowRotation { get; private set; }
    public System.Boolean brushing { get; }
    public Game.Tools.ObjectToolSystem+State state { get; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
    private System.Single cameraAngle { private get; }

    public ObjectToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    internal static System.Boolean <GetAllowDowngrade>g__Condition|143_0(Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Net.SubReplacement replacement);
    private System.Boolean <GetAllowUpgrade>g__Condition|142_0(Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Net.SubReplacement replacement);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void ElevationDown();
    public virtual System.Void ElevationScroll();
    public virtual System.Void ElevationUp();
    private Unity.Jobs.JobHandle FixNetControlPoints(Unity.Jobs.JobHandle inputDeps);
    protected virtual System.Boolean GetAllowApply();
    protected System.Boolean GetAllowDowngrade(System.Boolean& replacementExist);
    protected System.Boolean GetAllowPreciseRotation();
    protected System.Boolean GetAllowRotation();
    protected System.Boolean GetAllowUpgrade(System.Boolean& replacementExist);
    protected System.Boolean GetAllowUpgradeOrDowngrade(System.Func<Game.Tools.NetToolSystem+UpgradeState, Game.Net.SubReplacement, System.Boolean> condition, Game.Tools.ObjectToolSystem+State mode, System.Boolean& replacementExist);
    public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    private static System.Void GetAvailableSnapMask(Game.Prefabs.PlaceableObjectData prefabPlaceableData, System.Boolean editorMode, System.Boolean isBuilding, System.Boolean isAssetStamp, Game.Tools.ObjectToolSystem+Mode mode, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    public Unity.Collections.NativeList<Game.Tools.ControlPoint> GetControlPoints(Unity.Jobs.JobHandle& dependencies);
    private static System.Int32 GetMaxControlPointCount(Game.Tools.ObjectToolSystem+Mode mode);
    public Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> GetNetUpgradeStates(Unity.Jobs.JobHandle& dependencies);
    private Game.Prefabs.ObjectPrefab GetObjectPrefab();
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    public Unity.Collections.NativeList<Game.Tools.SubSnapPoint> GetSubSnapPoints(Unity.Jobs.JobHandle& dependencies);
    public virtual System.Void GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes);
    private Unity.Entities.Entity GetUpgradable(Unity.Entities.Entity entity);
    private System.Boolean HaveBrushSettingsChanged();
    public virtual System.Void InitializeRaycast();
    private System.Void InitializeRotation(Unity.Entities.Entity entity, Game.Prefabs.PlaceableObjectData placeableObjectData);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    private System.Void Randomize();
    private virtual System.Void ResetActions();
    private System.Void Rotate(System.Single angle, System.Boolean fromStart, System.Boolean align);
    private System.Void SetAppliedUpgrade(System.Boolean removing);
    public virtual System.Void SetUnderground(System.Boolean underground);
    private Unity.Jobs.JobHandle SnapControlPoint(Unity.Jobs.JobHandle inputDeps);
    public System.Void StartMoving(Unity.Entities.Entity movingObject);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle UpdateSubReplacementDefinitions(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Tools.ObjectToolSystem+Mode <mode>k__BackingField`  

```csharp
private Game.Tools.ObjectToolSystem+Mode <mode>k__BackingField;
```

- `private Game.Tools.AgeMask <ageMask>k__BackingField`  

```csharp
private Game.Tools.AgeMask <ageMask>k__BackingField;
```

- `private Game.Tools.Snap m_SelectedSnap`  

```csharp
private Game.Tools.Snap m_SelectedSnap;
```

- `private System.Single m_Distance`  

```csharp
private System.Single m_Distance;
```

- `private System.Single <distanceScale>k__BackingField`  

```csharp
private System.Single <distanceScale>k__BackingField;
```

- `private System.Boolean <underground>k__BackingField`  

```csharp
private System.Boolean <underground>k__BackingField;
```

- `private System.Boolean <allowCreate>k__BackingField`  

```csharp
private System.Boolean <allowCreate>k__BackingField;
```

- `private System.Boolean <allowLine>k__BackingField`  

```csharp
private System.Boolean <allowLine>k__BackingField;
```

- `private System.Boolean <allowCurve>k__BackingField`  

```csharp
private System.Boolean <allowCurve>k__BackingField;
```

- `private System.Boolean <allowBrush>k__BackingField`  

```csharp
private System.Boolean <allowBrush>k__BackingField;
```

- `private System.Boolean <allowStamp>k__BackingField`  

```csharp
private System.Boolean <allowStamp>k__BackingField;
```

- `private System.Boolean <allowAge>k__BackingField`  

```csharp
private System.Boolean <allowAge>k__BackingField;
```

- `private System.Boolean <allowRotation>k__BackingField`  

```csharp
private System.Boolean <allowRotation>k__BackingField;
```

- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  

```csharp
private Game.Tools.AreaToolSystem m_AreaToolSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  

```csharp
private Game.Zones.SearchSystem m_ZoneSearchSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_ContainerQuery`  

```csharp
private Unity.Entities.EntityQuery m_ContainerQuery;
```

- `private Unity.Entities.EntityQuery m_BrushQuery`  

```csharp
private Unity.Entities.EntityQuery m_BrushQuery;
```

- `private Unity.Entities.EntityQuery m_LotQuery`  

```csharp
private Unity.Entities.EntityQuery m_LotQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_VisibleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VisibleQuery;
```

- `private Game.Input.IProxyAction m_EraseObject`  

```csharp
private Game.Input.IProxyAction m_EraseObject;
```

- `private Game.Input.IProxyAction m_MoveObject`  

```csharp
private Game.Input.IProxyAction m_MoveObject;
```

- `private Game.Input.IProxyAction m_PaintObject`  

```csharp
private Game.Input.IProxyAction m_PaintObject;
```

- `private Game.Input.IProxyAction m_PlaceObject`  

```csharp
private Game.Input.IProxyAction m_PlaceObject;
```

- `private Game.Input.IProxyAction m_PlaceUpgrade`  

```csharp
private Game.Input.IProxyAction m_PlaceUpgrade;
```

- `private Game.Input.IProxyAction m_PreciseRotation`  

```csharp
private Game.Input.IProxyAction m_PreciseRotation;
```

- `private Game.Input.IProxyAction m_RotateObject`  

```csharp
private Game.Input.IProxyAction m_RotateObject;
```

- `private Game.Input.IProxyAction m_PlaceNetEdge`  

```csharp
private Game.Input.IProxyAction m_PlaceNetEdge;
```

- `private Game.Input.IProxyAction m_PlaceNetControlPoint`  

```csharp
private Game.Input.IProxyAction m_PlaceNetControlPoint;
```

- `private Game.Input.IProxyAction m_UndoNetControlPoint`  

```csharp
private Game.Input.IProxyAction m_UndoNetControlPoint;
```

- `private Game.Input.IProxyAction m_DowngradeNetEdge`  

```csharp
private Game.Input.IProxyAction m_DowngradeNetEdge;
```

- `private Game.Input.IProxyAction m_UpgradeNetEdge`  

```csharp
private Game.Input.IProxyAction m_UpgradeNetEdge;
```

- `private Game.Input.IProxyAction m_DiscardUpgrade`  

```csharp
private Game.Input.IProxyAction m_DiscardUpgrade;
```

- `private Game.Input.IProxyAction m_DiscardDowngrade`  

```csharp
private Game.Input.IProxyAction m_DiscardDowngrade;
```

- `private Game.Input.IProxyAction m_ReplaceNetEdge`  

```csharp
private Game.Input.IProxyAction m_ReplaceNetEdge;
```

- `private System.Boolean m_ApplyBlocked`  

```csharp
private System.Boolean m_ApplyBlocked;
```

- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  

```csharp
private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
```

- `private Unity.Collections.NativeList<Game.Tools.SubSnapPoint> m_SubSnapPoints`  

```csharp
private Unity.Collections.NativeList<Game.Tools.SubSnapPoint> m_SubSnapPoints;
```

- `private Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> m_UpgradeStates`  

```csharp
private Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState> m_UpgradeStates;
```

- `private Unity.Collections.NativeReference<Game.Tools.ObjectToolSystem+Rotation> m_Rotation`  

```csharp
private Unity.Collections.NativeReference<Game.Tools.ObjectToolSystem+Rotation> m_Rotation;
```

- `private Unity.Collections.NativeReference<Game.Tools.NetToolSystem+AppliedUpgrade> m_AppliedUpgrade`  

```csharp
private Unity.Collections.NativeReference<Game.Tools.NetToolSystem+AppliedUpgrade> m_AppliedUpgrade;
```

- `private Game.Tools.ControlPoint m_LastRaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_LastRaycastPoint;
```

- `private Game.Tools.ControlPoint m_StartPoint`  

```csharp
private Game.Tools.ControlPoint m_StartPoint;
```

- `private Unity.Entities.Entity m_UpgradingObject`  

```csharp
private Unity.Entities.Entity m_UpgradingObject;
```

- `private Unity.Entities.Entity m_MovingObject`  

```csharp
private Unity.Entities.Entity m_MovingObject;
```

- `private Unity.Entities.Entity m_MovingInitialized`  

```csharp
private Unity.Entities.Entity m_MovingInitialized;
```

- `private Game.Tools.ObjectToolSystem+State m_State`  

```csharp
private Game.Tools.ObjectToolSystem+State m_State;
```

- `private Game.Tools.ObjectToolSystem+Mode m_LastActualMode`  

```csharp
private Game.Tools.ObjectToolSystem+Mode m_LastActualMode;
```

- `private System.Boolean m_RotationModified`  

```csharp
private System.Boolean m_RotationModified;
```

- `private System.Boolean m_ForceCancel`  

```csharp
private System.Boolean m_ForceCancel;
```

- `private Unity.Mathematics.float3 m_RotationStartPosition`  

```csharp
private Unity.Mathematics.float3 m_RotationStartPosition;
```

- `private Unity.Mathematics.quaternion m_StartRotation`  

```csharp
private Unity.Mathematics.quaternion m_StartRotation;
```

- `private System.Single m_StartCameraAngle`  

```csharp
private System.Single m_StartCameraAngle;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Game.Common.RandomSeed m_RandomSeed`  

```csharp
private Game.Common.RandomSeed m_RandomSeed;
```

- `private Game.Prefabs.ObjectPrefab m_Prefab`  

```csharp
private Game.Prefabs.ObjectPrefab m_Prefab;
```

- `private Game.Prefabs.ObjectPrefab m_SelectedPrefab`  

```csharp
private Game.Prefabs.ObjectPrefab m_SelectedPrefab;
```

- `private Game.Prefabs.TransformPrefab m_TransformPrefab`  

```csharp
private Game.Prefabs.TransformPrefab m_TransformPrefab;
```

- `private Game.CameraController m_CameraController`  

```csharp
private Game.CameraController m_CameraController;
```

- `private Game.Tools.ObjectToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ObjectToolSystem+TypeHandle __TypeHandle;
```

- `public static const System.String kToolID`  

```csharp
public static const System.String kToolID;
```

- `private static const System.String kTree`  

```csharp
private static const System.String kTree;
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

- `public Game.Tools.ObjectToolSystem+Mode mode { get; set }`  

```csharp
public Game.Tools.ObjectToolSystem+Mode mode { get; set; }
```

- `public Game.Tools.ObjectToolSystem+Mode actualMode { get }`  

```csharp
public Game.Tools.ObjectToolSystem+Mode actualMode { get; }
```

- `public System.Boolean isUpgradeMode { get }`  

```csharp
public System.Boolean isUpgradeMode { get; }
```

- `public Game.Tools.AgeMask ageMask { get; set }`  

```csharp
public Game.Tools.AgeMask ageMask { get; set; }
```

- `public Game.Tools.AgeMask actualAgeMask { get }`  

```csharp
public Game.Tools.AgeMask actualAgeMask { get; }
```

- `public Game.Prefabs.ObjectPrefab prefab { get; set }`  

```csharp
public Game.Prefabs.ObjectPrefab prefab { get; set; }
```

- `public Game.Prefabs.TransformPrefab transform { get; set }`  

```csharp
public Game.Prefabs.TransformPrefab transform { get; set; }
```

- `public Game.Tools.Snap selectedSnap { get; set }`  

```csharp
public Game.Tools.Snap selectedSnap { get; set; }
```

- `public System.Single distance { get; set }`  

```csharp
public System.Single distance { get; set; }
```

- `public System.Single distanceScale { get; private set }`  

```csharp
public System.Single distanceScale { get; private set; }
```

- `public System.Boolean underground { get; set }`  

```csharp
public System.Boolean underground { get; set; }
```

- `public System.Boolean allowCreate { get; private set }`  

```csharp
public System.Boolean allowCreate { get; private set; }
```

- `public System.Boolean allowLine { get; private set }`  

```csharp
public System.Boolean allowLine { get; private set; }
```

- `public System.Boolean allowCurve { get; private set }`  

```csharp
public System.Boolean allowCurve { get; private set; }
```

- `public System.Boolean allowBrush { get; private set }`  

```csharp
public System.Boolean allowBrush { get; private set; }
```

- `public System.Boolean allowStamp { get; private set }`  

```csharp
public System.Boolean allowStamp { get; private set; }
```

- `public System.Boolean allowAge { get; private set }`  

```csharp
public System.Boolean allowAge { get; private set; }
```

- `public System.Boolean allowRotation { get; private set }`  

```csharp
public System.Boolean allowRotation { get; private set; }
```

- `public System.Boolean brushing { get }`  

```csharp
public System.Boolean brushing { get; }
```

- `public Game.Tools.ObjectToolSystem+State state { get }`  

```csharp
public Game.Tools.ObjectToolSystem+State state { get; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```

- `private System.Single cameraAngle { private get }`  

```csharp
private System.Single cameraAngle { private get; }
```


## Constructors

- `public ObjectToolSystem()`  

```csharp
[Preserve]
	public ObjectToolSystem()
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

- `internal static <GetAllowDowngrade>g__Condition|143_0(Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Net.SubReplacement replacement) : System.Boolean`  

```csharp
internal static System.Boolean <GetAllowDowngrade>g__Condition|143_0(Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Net.SubReplacement replacement);
```

- `private <GetAllowUpgrade>g__Condition|142_0(Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Net.SubReplacement replacement) : System.Boolean`  

```csharp
private System.Boolean <GetAllowUpgrade>g__Condition|142_0(Game.Tools.NetToolSystem+UpgradeState upgradeState, Game.Net.SubReplacement replacement);
```

- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Apply(JobHandle inputDeps, bool singleFrameOnly = false)
	{
		if (actualMode == Mode.Brush)
		{
			bool allowApply = GetAllowApply();
			if (m_State == State.Default)
			{
				base.applyMode = (allowApply ? ApplyMode.Apply : ApplyMode.Clear);
				Randomize();
				if (!singleFrameOnly)
				{
					m_StartPoint = m_LastRaycastPoint;
					m_State = State.Adding;
				}
				GetRaycastResult(out m_LastRaycastPoint);
				return UpdateDefinitions(inputDeps);
			}
			if (m_State == State.Adding && allowApply)
			{
				base.applyMode = ApplyMode.Apply;
				Randomize();
				m_StartPoint = default(ControlPoint);
				m_State = State.Default;
				GetRaycastResult(out m_LastRaycastPoint);
				return UpdateDefinitions(inputDeps);
			}
			base.applyMode = ApplyMode.Clear;
			m_StartPoint = default(ControlPoint);
			m_State = State.Default;
			GetRaycastResult(out m_LastRaycastPoint);
			return UpdateDefinitions(inputDeps);
		}
		if (m_State != State.Adding && m_UpgradeStates.Length >= 1 && !singleFrameOnly)
		{
			m_State = State.Adding;
			m_ForceUpdate = true;
			m_AppliedUpgrade.Value = default(NetToolSystem.AppliedUpgrade);
			return Update(inputDeps, fullUpdate: true);
		}
		if (m_State == State.Adding)
		{
			m_State = State.Default;
			if (GetAllowApply())
			{
				SetAppliedUpgrade(removing: false);
				base.applyMode = ApplyMode.Apply;
				m_RandomSeed = RandomSeed.Next();
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_NetBuildSound);
				m_ControlPoints.Clear();
				m_UpgradeStates.Clear();
				if (GetRaycastResult(out var controlPoint))
				{
					m_ControlPoints.Add(in controlPoint);
					inputDeps = SnapControlPoint(inputDeps);
					inputDeps = FixNetControlPoints(inputDeps);
					inputDeps = UpdateDefinitions(inputDeps);
				}
				else
				{
					inputDeps = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
				}
			}
			else
			{
				m_ControlPoints.Clear();
				m_UpgradeStates.Clear();
				m_ForceUpdate = true;
				inputDeps = Update(inputDeps, fullUpdate: true);
			}
			return inputDeps;
		}
		if (m_ControlPoints.Length < GetMaxControlPointCount(actualMode))
		{
			base.applyMode = ApplyMode.Clear;
			if (GetRaycastResult(out var controlPoint2))
			{
				if (m_ControlPoints.Length <= 1)
				{
					m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_NetStartSound);
				}
				else
				{
					m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_NetNodeSound);
				}
				controlPoint2.m_Rotation = m_Rotation.Value.m_Rotation;
				m_ControlPoints.Add(in controlPoint2);
				inputDeps = SnapControlPoint(inputDeps);
				inputDeps = UpdateDefinitions(inputDeps);
			}
			else
			{
				inputDeps = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
			}
		}
		else if (GetAllowApply())
		{
			base.applyMode = ApplyMode.Apply;
			Randomize();
			if (m_Prefab is BuildingPrefab || m_Prefab is AssetStampPrefab)
			{
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PlaceBuildingSound);
			}
			else if (m_Prefab is StaticObjectPrefab || m_ToolSystem.actionMode.IsEditor())
			{
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PlacePropSound);
			}
			m_ControlPoints.Clear();
			m_UpgradeStates.Clear();
			m_AppliedUpgrade.Value = default(NetToolSystem.AppliedUpgrade);
			if (m_ToolSystem.actionMode.IsGame() && !m_LotQuery.IsEmptyIgnoreFilter)
			{
				NativeArray<Entity> nativeArray = m_LotQuery.ToEntityArray(Allocator.TempJob);
				try
				{
					for (int i = 0; i < nativeArray.Length; i++)
					{
						Entity entity = nativeArray[i];
						Area componentData = base.EntityManager.GetComponentData<Area>(entity);
						Temp componentData2 = base.EntityManager.GetComponentData<Temp>(entity);
						if ((componentData.m_Flags & AreaFlags.Slave) == 0 && (componentData2.m_Flags & TempFlags.Create) != 0)
						{
							LotPrefab lotPrefab = m_PrefabSystem.GetPrefab<LotPrefab>(base.EntityManager.GetComponentData<PrefabRef>(entity));
							if (!lotPrefab.m_AllowOverlap)
							{
								m_AreaToolSystem.recreate = entity;
								m_AreaToolSystem.prefab = lotPrefab;
								m_AreaToolSystem.mode = AreaToolSystem.Mode.Edit;
								m_ToolSystem.activeTool = m_AreaToolSystem;
								return inputDeps;
							}
						}
					}
				}
				finally
				{
					nativeArray.Dispose();
				}
			}
			if (GetRaycastResult(out var controlPoint3))
			{
				if (m_ToolSystem.actionMode.IsGame())
				{
					Telemetry.PlaceBuilding(m_UpgradingObject, m_Prefab, controlPoint3.m_Position);
				}
				controlPoint3.m_Rotation = m_Rotation.Value.m_Rotation;
				m_ControlPoints.Add(in controlPoint3);
				inputDeps = SnapControlPoint(inputDeps);
				inputDeps = UpdateDefinitions(inputDeps);
			}
		}
		else
		{
			m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PlaceBuildingFailSound);
			inputDeps = Update(inputDeps, fullUpdate: false);
		}
		return inputDeps;
	}
```

- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Cancel(JobHandle inputDeps, bool singleFrameOnly = false)
	{
		if (actualMode == Mode.Brush)
		{
			if (m_State == State.Default)
			{
				base.applyMode = ApplyMode.Clear;
				Randomize();
				m_StartPoint = m_LastRaycastPoint;
				m_State = State.Removing;
				m_ForceCancel = singleFrameOnly;
				GetRaycastResult(out m_LastRaycastPoint);
				return UpdateDefinitions(inputDeps);
			}
			if (m_State == State.Removing && GetAllowApply())
			{
				base.applyMode = ApplyMode.Apply;
				Randomize();
				m_StartPoint = default(ControlPoint);
				m_State = State.Default;
				GetRaycastResult(out m_LastRaycastPoint);
				return UpdateDefinitions(inputDeps);
			}
			base.applyMode = ApplyMode.Clear;
			m_StartPoint = default(ControlPoint);
			m_State = State.Default;
			GetRaycastResult(out m_LastRaycastPoint);
			return UpdateDefinitions(inputDeps);
		}
		if (m_State != State.Removing && m_UpgradeStates.Length >= 1)
		{
			m_State = State.Removing;
			m_ForceCancel = singleFrameOnly;
			m_ForceUpdate = true;
			m_AppliedUpgrade.Value = default(NetToolSystem.AppliedUpgrade);
			return Update(inputDeps, fullUpdate: true);
		}
		if (m_State == State.Removing)
		{
			m_State = State.Default;
			if (GetAllowApply())
			{
				SetAppliedUpgrade(removing: true);
				base.applyMode = ApplyMode.Apply;
				m_RandomSeed = RandomSeed.Next();
				m_ControlPoints.Clear();
				m_UpgradeStates.Clear();
				if (GetRaycastResult(out var controlPoint))
				{
					m_ControlPoints.Add(in controlPoint);
					inputDeps = SnapControlPoint(inputDeps);
					inputDeps = FixNetControlPoints(inputDeps);
					inputDeps = UpdateDefinitions(inputDeps);
					m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PolygonToolRemovePointSound);
				}
				else
				{
					inputDeps = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
				}
			}
			else
			{
				base.applyMode = ApplyMode.Clear;
				m_ControlPoints.Clear();
				m_UpgradeStates.Clear();
				if (GetRaycastResult(out var controlPoint2))
				{
					m_ControlPoints.Add(in controlPoint2);
					inputDeps = SnapControlPoint(inputDeps);
					inputDeps = UpdateDefinitions(inputDeps);
				}
				else
				{
					inputDeps = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
				}
			}
			return inputDeps;
		}
		if ((actualMode != Mode.Upgrade || (m_SnapOnMask & ~m_SnapOffMask & Snap.OwnerSide) == 0) && m_ControlPoints.Length <= 1)
		{
			if (singleFrameOnly)
			{
				Rotate(MathF.PI / 4f, fromStart: false, align: true);
			}
			else
			{
				m_State = State.Rotating;
				m_RotationStartPosition = InputManager.instance.mousePosition;
				m_StartRotation = m_Rotation.Value.m_Rotation;
				m_StartCameraAngle = cameraAngle;
			}
		}
		base.applyMode = ApplyMode.Clear;
		if (m_ControlPoints.Length > 0)
		{
			m_ControlPoints.RemoveAt(m_ControlPoints.Length - 1);
		}
		m_UpgradeStates.Clear();
		m_AppliedUpgrade.Value = default(NetToolSystem.AppliedUpgrade);
		if (GetRaycastResult(out var controlPoint3))
		{
			controlPoint3.m_Rotation = m_Rotation.Value.m_Rotation;
			if (m_ControlPoints.Length > 0)
			{
				m_ControlPoints[m_ControlPoints.Length - 1] = controlPoint3;
			}
			else
			{
				m_ControlPoints.Add(in controlPoint3);
			}
			inputDeps = SnapControlPoint(inputDeps);
			inputDeps = UpdateDefinitions(inputDeps);
		}
		return inputDeps;
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

- `private FixNetControlPoints(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle FixNetControlPoints(JobHandle inputDeps)
	{
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> chunks = m_TempQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = IJobExtensions.Schedule(new NetToolSystem.FixControlPointsJob
		{
			m_Chunks = chunks,
			m_Mode = NetToolSystem.Mode.Replace,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ControlPoints = m_ControlPoints
		}, JobHandle.CombineDependencies(inputDeps, outJobHandle));
		chunks.Dispose(jobHandle);
		return jobHandle;
	}
```

- `protected virtual GetAllowApply() : System.Boolean`  

```csharp
protected override bool GetAllowApply()
	{
		if (base.GetAllowApply())
		{
			return !m_TempQuery.IsEmptyIgnoreFilter;
		}
		return false;
	}
```

- `protected GetAllowDowngrade(System.Boolean& replacementExist) : System.Boolean`  

```csharp
protected bool GetAllowDowngrade(out bool replacementExist)
	{
		return GetAllowUpgradeOrDowngrade(Condition, State.Removing, out replacementExist);
		static bool Condition(NetToolSystem.UpgradeState upgradeState, SubReplacement replacement)
		{
			return replacement.m_Side == upgradeState.m_SubReplacementSide;
		}
	}
```

- `protected GetAllowPreciseRotation() : System.Boolean`  

```csharp
protected bool GetAllowPreciseRotation()
	{
		if (GetAllowRotation())
		{
			if (!InputManager.instance.isGamepadControlSchemeActive)
			{
				return !InputManager.instance.mouseOverUI;
			}
			return true;
		}
		return false;
	}
```

- `protected GetAllowRotation() : System.Boolean`  

```csharp
protected bool GetAllowRotation()
	{
		if (allowRotation)
		{
			return !m_Rotation.Value.m_IsSnapped;
		}
		return false;
	}
```

- `protected GetAllowUpgrade(System.Boolean& replacementExist) : System.Boolean`  

```csharp
protected bool GetAllowUpgrade(out bool replacementExist)
	{
		return GetAllowUpgradeOrDowngrade(Condition, State.Adding, out replacementExist);
		bool Condition(NetToolSystem.UpgradeState upgradeState, SubReplacement replacement)
		{
			if (upgradeState.m_SubReplacementPrefab == Entity.Null)
			{
				return true;
			}
			if (replacement.m_Side == upgradeState.m_SubReplacementSide && replacement.m_AgeMask == actualAgeMask)
			{
				return replacement.m_Prefab == upgradeState.m_SubReplacementPrefab;
			}
			return false;
		}
	}
```

- `protected GetAllowUpgradeOrDowngrade(System.Func<Game.Tools.NetToolSystem+UpgradeState, Game.Net.SubReplacement, System.Boolean> condition, Game.Tools.ObjectToolSystem+State mode, System.Boolean& replacementExist) : System.Boolean`  

```csharp
protected bool GetAllowUpgradeOrDowngrade(Func<NetToolSystem.UpgradeState, SubReplacement, bool> condition, State mode, out bool replacementExist)
	{
		replacementExist = false;
		if (m_UpgradeStates.Length == 0 || m_ControlPoints.Length < 4)
		{
			return false;
		}
		ref NativeList<ControlPoint> reference = ref m_ControlPoints;
		Entity originalEntity = reference[reference.Length - 3].m_OriginalEntity;
		ref NativeList<ControlPoint> reference2 = ref m_ControlPoints;
		Entity originalEntity2 = reference2[reference2.Length - 2].m_OriginalEntity;
		if (!base.EntityManager.TryGetBuffer(originalEntity, isReadOnly: true, out DynamicBuffer<ConnectedEdge> buffer))
		{
			return false;
		}
		for (int i = 0; i < buffer.Length; i++)
		{
			Entity edge = buffer[i].m_Edge;
			if (!base.EntityManager.TryGetComponent<Edge>(edge, out var component) || ((component.m_Start != originalEntity || component.m_End != originalEntity2) && (component.m_End != originalEntity || component.m_Start != originalEntity2)))
			{
				continue;
			}
			if (!base.EntityManager.TryGetBuffer(edge, isReadOnly: true, out DynamicBuffer<SubReplacement> buffer2))
			{
				return mode switch
				{
					State.Adding => true, 
					State.Removing => false, 
					_ => false, 
				};
			}
			for (int j = 0; j < buffer2.Length; j++)
			{
				SubReplacement arg = buffer2[j];
				if (arg.m_Side == m_UpgradeStates[0].m_SubReplacementSide)
				{
					replacementExist = true;
				}
				if (condition(m_UpgradeStates[0], arg))
				{
					return mode switch
					{
						State.Adding => false, 
						State.Removing => true, 
						_ => false, 
					};
				}
			}
			return mode switch
			{
				State.Adding => true, 
				State.Removing => false, 
				_ => false, 
			};
		}
		return false;
	}
```

- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
private static void GetAvailableSnapMask(PlaceableObjectData prefabPlaceableData, bool editorMode, bool isBuilding, bool isAssetStamp, Mode mode, out Snap onMask, out Snap offMask)
	{
		onMask = Snap.Upright;
		offMask = Snap.None;
		if ((prefabPlaceableData.m_Flags & (Game.Objects.PlacementFlags.RoadSide | Game.Objects.PlacementFlags.OwnerSide)) == Game.Objects.PlacementFlags.OwnerSide)
		{
			onMask |= Snap.OwnerSide;
		}
		else if ((prefabPlaceableData.m_Flags & (Game.Objects.PlacementFlags.RoadSide | Game.Objects.PlacementFlags.Shoreline | Game.Objects.PlacementFlags.Floating | Game.Objects.PlacementFlags.Hovering)) != Game.Objects.PlacementFlags.None)
		{
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.OwnerSide) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.OwnerSide;
				offMask |= Snap.OwnerSide;
			}
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.RoadSide) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.NetSide;
				offMask |= Snap.NetSide;
			}
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.RoadEdge) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.NetArea;
				offMask |= Snap.NetArea;
			}
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.Shoreline) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.Shoreline;
				offMask |= Snap.Shoreline;
			}
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.Hovering) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.ObjectSurface;
				offMask |= Snap.ObjectSurface;
			}
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.SubNetSnap) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.ExistingGeometry;
				offMask |= Snap.ExistingGeometry;
			}
		}
		else if ((prefabPlaceableData.m_Flags & (Game.Objects.PlacementFlags.RoadNode | Game.Objects.PlacementFlags.RoadEdge)) != Game.Objects.PlacementFlags.None)
		{
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.RoadNode) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.NetNode;
			}
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.RoadEdge) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.NetArea;
			}
		}
		else
		{
			if (prefabPlaceableData.m_SubReplacementType != SubReplacementType.None && mode != Mode.Move)
			{
				onMask |= Snap.NetArea;
				offMask |= Snap.NetArea;
			}
			if (editorMode && !isBuilding)
			{
				onMask |= Snap.ObjectSurface;
				offMask |= Snap.ObjectSurface;
				offMask |= Snap.Upright;
			}
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.SubNetSnap) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.ExistingGeometry;
				offMask |= Snap.ExistingGeometry;
			}
		}
		if (editorMode && (!isAssetStamp || mode == Mode.Stamp))
		{
			onMask |= Snap.AutoParent;
			offMask |= Snap.AutoParent;
		}
		if (mode == Mode.Line || mode == Mode.Curve)
		{
			onMask |= Snap.Distance;
			offMask |= Snap.Distance;
		}
		if (mode == Mode.Curve || (editorMode && mode == Mode.Line))
		{
			onMask |= Snap.StraightDirection;
			offMask |= Snap.StraightDirection;
		}
		if (mode == Mode.Brush)
		{
			onMask &= Snap.Upright;
			offMask &= Snap.Upright;
			onMask |= Snap.PrefabType;
			offMask |= Snap.PrefabType;
		}
		if (isBuilding || isAssetStamp)
		{
			onMask |= Snap.ContourLines;
			offMask |= Snap.ContourLines;
		}
	}
```

- `private static GetAvailableSnapMask(Game.Prefabs.PlaceableObjectData prefabPlaceableData, System.Boolean editorMode, System.Boolean isBuilding, System.Boolean isAssetStamp, Game.Tools.ObjectToolSystem+Mode mode, Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
private static void GetAvailableSnapMask(PlaceableObjectData prefabPlaceableData, bool editorMode, bool isBuilding, bool isAssetStamp, Mode mode, out Snap onMask, out Snap offMask)
	{
		onMask = Snap.Upright;
		offMask = Snap.None;
		if ((prefabPlaceableData.m_Flags & (Game.Objects.PlacementFlags.RoadSide | Game.Objects.PlacementFlags.OwnerSide)) == Game.Objects.PlacementFlags.OwnerSide)
		{
			onMask |= Snap.OwnerSide;
		}
		else if ((prefabPlaceableData.m_Flags & (Game.Objects.PlacementFlags.RoadSide | Game.Objects.PlacementFlags.Shoreline | Game.Objects.PlacementFlags.Floating | Game.Objects.PlacementFlags.Hovering)) != Game.Objects.PlacementFlags.None)
		{
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.OwnerSide) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.OwnerSide;
				offMask |= Snap.OwnerSide;
			}
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.RoadSide) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.NetSide;
				offMask |= Snap.NetSide;
			}
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.RoadEdge) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.NetArea;
				offMask |= Snap.NetArea;
			}
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.Shoreline) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.Shoreline;
				offMask |= Snap.Shoreline;
			}
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.Hovering) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.ObjectSurface;
				offMask |= Snap.ObjectSurface;
			}
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.SubNetSnap) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.ExistingGeometry;
				offMask |= Snap.ExistingGeometry;
			}
		}
		else if ((prefabPlaceableData.m_Flags & (Game.Objects.PlacementFlags.RoadNode | Game.Objects.PlacementFlags.RoadEdge)) != Game.Objects.PlacementFlags.None)
		{
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.RoadNode) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.NetNode;
			}
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.RoadEdge) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.NetArea;
			}
		}
		else
		{
			if (prefabPlaceableData.m_SubReplacementType != SubReplacementType.None && mode != Mode.Move)
			{
				onMask |= Snap.NetArea;
				offMask |= Snap.NetArea;
			}
			if (editorMode && !isBuilding)
			{
				onMask |= Snap.ObjectSurface;
				offMask |= Snap.ObjectSurface;
				offMask |= Snap.Upright;
			}
			if ((prefabPlaceableData.m_Flags & Game.Objects.PlacementFlags.SubNetSnap) != Game.Objects.PlacementFlags.None)
			{
				onMask |= Snap.ExistingGeometry;
				offMask |= Snap.ExistingGeometry;
			}
		}
		if (editorMode && (!isAssetStamp || mode == Mode.Stamp))
		{
			onMask |= Snap.AutoParent;
			offMask |= Snap.AutoParent;
		}
		if (mode == Mode.Line || mode == Mode.Curve)
		{
			onMask |= Snap.Distance;
			offMask |= Snap.Distance;
		}
		if (mode == Mode.Curve || (editorMode && mode == Mode.Line))
		{
			onMask |= Snap.StraightDirection;
			offMask |= Snap.StraightDirection;
		}
		if (mode == Mode.Brush)
		{
			onMask &= Snap.Upright;
			offMask &= Snap.Upright;
			onMask |= Snap.PrefabType;
			offMask |= Snap.PrefabType;
		}
		if (isBuilding || isAssetStamp)
		{
			onMask |= Snap.ContourLines;
			offMask |= Snap.ContourLines;
		}
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

- `private static GetMaxControlPointCount(Game.Tools.ObjectToolSystem+Mode mode) : System.Int32`  

```csharp
private static int GetMaxControlPointCount(Mode mode)
	{
		return mode switch
		{
			Mode.Brush => 0, 
			Mode.Line => 2, 
			Mode.Curve => 3, 
			_ => 1, 
		};
	}
```

- `public GetNetUpgradeStates(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.NetToolSystem+UpgradeState>`  

```csharp
public NativeList<NetToolSystem.UpgradeState> GetNetUpgradeStates(out JobHandle dependencies)
	{
		dependencies = base.Dependency;
		return m_UpgradeStates;
	}
```

- `private GetObjectPrefab() : Game.Prefabs.ObjectPrefab`  

```csharp
private ObjectPrefab GetObjectPrefab()
	{
		if (m_ToolSystem.actionMode.IsEditor() && m_TransformPrefab != null && GetContainers(m_ContainerQuery, out var _, out var transformContainer))
		{
			return m_PrefabSystem.GetPrefab<ObjectPrefab>(transformContainer);
		}
		if (actualMode == Mode.Move)
		{
			Entity entity = m_MovingObject;
			if (m_ToolSystem.actionMode.IsEditor() && base.EntityManager.HasComponent<Game.Buildings.ServiceUpgrade>(entity) && base.EntityManager.TryGetComponent<Owner>(entity, out var component))
			{
				entity = component.m_Owner;
			}
			if (base.EntityManager.TryGetComponent<PrefabRef>(entity, out var component2))
			{
				return m_PrefabSystem.GetPrefab<ObjectPrefab>(component2);
			}
		}
		return m_SelectedPrefab;
	}
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public override PrefabBase GetPrefab()
	{
		Mode mode = actualMode;
		if (mode == Mode.Create || (uint)(mode - 3) <= 3u)
		{
			if (!(prefab != null))
			{
				return transform;
			}
			return prefab;
		}
		return null;
	}
```

- `public GetSubSnapPoints(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Tools.SubSnapPoint>`  

```csharp
public NativeList<SubSnapPoint> GetSubSnapPoints(out JobHandle dependencies)
	{
		dependencies = base.Dependency;
		return m_SubSnapPoints;
	}
```

- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  

```csharp
public override void GetUIModes(List<ToolMode> modes)
	{
		Mode mode = this.mode;
		if (mode != Mode.Create && (uint)(mode - 3) > 3u)
		{
			return;
		}
		if (allowCreate)
		{
			if (prefab != null && prefab.Has<TreeObject>())
			{
				modes.Add(new ToolMode(Mode.Create.ToString() + "Tree", 0));
			}
			else
			{
				modes.Add(new ToolMode(Mode.Create.ToString(), 0));
			}
		}
		if (allowLine)
		{
			modes.Add(new ToolMode(Mode.Line.ToString(), 5));
		}
		if (allowCurve)
		{
			modes.Add(new ToolMode(Mode.Curve.ToString(), 6));
		}
		if (allowBrush)
		{
			modes.Add(new ToolMode(Mode.Brush.ToString(), 3));
		}
		if (allowStamp)
		{
			modes.Add(new ToolMode(Mode.Stamp.ToString(), 4));
		}
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

- `private HaveBrushSettingsChanged() : System.Boolean`  

```csharp
private bool HaveBrushSettingsChanged()
	{
		NativeArray<ArchetypeChunk> nativeArray = m_VisibleQuery.ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			ComponentTypeHandle<Brush> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Brush_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				NativeArray<Brush> nativeArray2 = nativeArray[i].GetNativeArray(ref typeHandle);
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					if (!nativeArray2[j].m_Size.Equals(base.brushSize))
					{
						return true;
					}
				}
			}
			return false;
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public override void InitializeRaycast()
	{
		base.InitializeRaycast();
		m_Prefab = GetObjectPrefab();
		if (m_Prefab != null)
		{
			float3 rayOffset = default(float3);
			Bounds3 bounds = default(Bounds3);
			if (m_PrefabSystem.TryGetComponentData<ObjectGeometryData>(m_Prefab, out var component))
			{
				rayOffset.y -= component.m_Pivot.y;
				bounds = component.m_Bounds;
			}
			if (m_PrefabSystem.TryGetComponentData<PlaceableObjectData>(m_Prefab, out var component2))
			{
				rayOffset.y -= component2.m_PlacementOffset.y;
				if ((component2.m_Flags & Game.Objects.PlacementFlags.Hanging) != Game.Objects.PlacementFlags.None)
				{
					rayOffset.y += bounds.max.y;
				}
			}
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.IgnoreSecondary;
			m_ToolRaycastSystem.rayOffset = rayOffset;
			GetAvailableSnapMask(out var onMask, out var offMask);
			Snap snap = ToolBaseSystem.GetActualSnap(selectedSnap, onMask, offMask);
			Mode mode = actualMode;
			if (component2.m_SubReplacementType != SubReplacementType.None && (snap & Snap.NetArea) != Snap.None && (mode == Mode.Line || mode == Mode.Curve) && m_UpgradeStates.Length == 0 && m_ControlPoints.Length >= 2 && m_State != State.Adding && m_State != State.Removing)
			{
				snap = (Snap)((uint)snap & 0xFFFFFFEFu);
			}
			if ((snap & (Snap.NetArea | Snap.NetNode)) != Snap.None)
			{
				m_ToolRaycastSystem.typeMask |= TypeMask.Net;
				m_ToolRaycastSystem.netLayerMask |= Layer.Road | Layer.TrainTrack | Layer.TramTrack | Layer.SubwayTrack | Layer.PublicTransportRoad;
			}
			if ((snap & Snap.ObjectSurface) != Snap.None)
			{
				m_ToolRaycastSystem.typeMask |= TypeMask.StaticObjects;
				if (m_ToolSystem.actionMode.IsEditor())
				{
					m_ToolRaycastSystem.raycastFlags |= RaycastFlags.Placeholders;
				}
			}
			if ((snap & (Snap.NetArea | Snap.NetNode | Snap.ObjectSurface)) != Snap.None && !m_PrefabSystem.HasComponent<BuildingData>(m_Prefab))
			{
				if (underground)
				{
					m_ToolRaycastSystem.collisionMask = CollisionMask.Underground;
					m_ToolRaycastSystem.raycastFlags |= RaycastFlags.PartialSurface;
				}
				else
				{
					m_ToolRaycastSystem.typeMask |= TypeMask.Terrain;
					if ((component2.m_Flags & (Game.Objects.PlacementFlags.Shoreline | Game.Objects.PlacementFlags.Floating | Game.Objects.PlacementFlags.Hovering)) != Game.Objects.PlacementFlags.None)
					{
						m_ToolRaycastSystem.typeMask |= TypeMask.Water;
					}
					m_ToolRaycastSystem.raycastFlags |= RaycastFlags.Outside;
					m_ToolRaycastSystem.collisionMask = CollisionMask.OnGround | CollisionMask.Overground;
				}
			}
			else
			{
				m_ToolRaycastSystem.typeMask |= TypeMask.Terrain;
				if ((component2.m_Flags & (Game.Objects.PlacementFlags.Shoreline | Game.Objects.PlacementFlags.Floating | Game.Objects.PlacementFlags.Hovering)) != Game.Objects.PlacementFlags.None)
				{
					m_ToolRaycastSystem.typeMask |= TypeMask.Water;
				}
				m_ToolRaycastSystem.raycastFlags |= RaycastFlags.Outside;
				m_ToolRaycastSystem.netLayerMask |= Layer.None;
			}
		}
		else
		{
			m_ToolRaycastSystem.typeMask = TypeMask.Terrain | TypeMask.Water;
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.Outside;
			m_ToolRaycastSystem.netLayerMask = Layer.None;
			m_ToolRaycastSystem.rayOffset = default(float3);
		}
		if (m_ToolSystem.actionMode.IsEditor())
		{
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.SubElements;
		}
	}
```

- `private InitializeRotation(Unity.Entities.Entity entity, Game.Prefabs.PlaceableObjectData placeableObjectData) : System.Void`  

```csharp
private void InitializeRotation(Entity entity, PlaceableObjectData placeableObjectData)
	{
		Rotation value = new Rotation
		{
			m_Rotation = quaternion.identity,
			m_ParentRotation = quaternion.identity,
			m_IsAligned = true
		};
		if (base.EntityManager.TryGetComponent<Game.Objects.Transform>(entity, out var component))
		{
			value.m_Rotation = component.m_Rotation;
		}
		if (base.EntityManager.TryGetComponent<Owner>(entity, out var component2))
		{
			Entity owner = component2.m_Owner;
			if (base.EntityManager.TryGetComponent<Game.Objects.Transform>(owner, out var component3))
			{
				value.m_ParentRotation = component3.m_Rotation;
			}
			while (base.EntityManager.TryGetComponent<Owner>(owner, out component2) && !base.EntityManager.HasComponent<Building>(owner))
			{
				owner = component2.m_Owner;
				if (base.EntityManager.TryGetComponent<Game.Objects.Transform>(owner, out component3))
				{
					value.m_ParentRotation = component3.m_Rotation;
				}
			}
		}
		quaternion rotation = value.m_Rotation;
		if ((placeableObjectData.m_Flags & Game.Objects.PlacementFlags.Wall) != Game.Objects.PlacementFlags.None)
		{
			SnapJob.AlignRotation(ref rotation, value.m_ParentRotation, zAxis: true);
		}
		else
		{
			SnapJob.AlignRotation(ref rotation, value.m_ParentRotation, zAxis: false);
		}
		if (MathUtils.RotationAngle(value.m_Rotation, rotation) > 0.01f)
		{
			value.m_IsAligned = false;
		}
		m_Rotation.Value = value;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolOutputBarrier = base.World.GetOrCreateSystemManaged<ToolOutputBarrier>();
		m_AreaToolSystem = base.World.GetOrCreateSystemManaged<AreaToolSystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_ZoneSearchSystem = base.World.GetOrCreateSystemManaged<Game.Zones.SearchSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_DefinitionQuery = GetDefinitionQuery();
		m_ContainerQuery = GetContainerQuery();
		m_BrushQuery = GetBrushQuery();
		m_ControlPoints = new NativeList<ControlPoint>(1, Allocator.Persistent);
		m_SubSnapPoints = new NativeList<SubSnapPoint>(10, Allocator.Persistent);
		m_UpgradeStates = new NativeList<NetToolSystem.UpgradeState>(10, Allocator.Persistent);
		m_Rotation = new NativeReference<Rotation>(Allocator.Persistent);
		m_AppliedUpgrade = new NativeReference<NetToolSystem.AppliedUpgrade>(Allocator.Persistent);
		m_Rotation.Value = new Rotation
		{
			m_Rotation = quaternion.identity,
			m_ParentRotation = quaternion.identity,
			m_IsAligned = true
		};
		m_SoundQuery = GetEntityQuery(ComponentType.ReadOnly<ToolUXSoundSettingsData>());
		m_LotQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Areas.Lot>(), ComponentType.ReadOnly<Temp>());
		m_BuildingQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingData>(), ComponentType.ReadOnly<SpawnableBuildingData>(), ComponentType.ReadOnly<BuildingSpawnGroupData>(), ComponentType.ReadOnly<PrefabData>());
		m_TempQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>());
		m_VisibleQuery = GetEntityQuery(ComponentType.ReadOnly<Brush>(), ComponentType.Exclude<Hidden>(), ComponentType.Exclude<Deleted>());
		m_EraseObject = InputManager.instance.toolActionCollection.GetActionState("Erase Object", "ObjectToolSystem");
		m_MoveObject = InputManager.instance.toolActionCollection.GetActionState("Move Object", "ObjectToolSystem");
		m_PaintObject = InputManager.instance.toolActionCollection.GetActionState("Paint Object", "ObjectToolSystem");
		m_PlaceObject = InputManager.instance.toolActionCollection.GetActionState("Place Object", "ObjectToolSystem");
		m_PlaceUpgrade = InputManager.instance.toolActionCollection.GetActionState("Place Upgrade", "ObjectToolSystem");
		m_PreciseRotation = InputManager.instance.toolActionCollection.GetActionState("Precise Rotation", "ObjectToolSystem");
		m_RotateObject = InputManager.instance.toolActionCollection.GetActionState("Rotate Object", "ObjectToolSystem");
		m_PlaceNetEdge = InputManager.instance.toolActionCollection.GetActionState("Place Net Edge", "ObjectToolSystem");
		m_PlaceNetControlPoint = InputManager.instance.toolActionCollection.GetActionState("Place Net Control Point", "ObjectToolSystem");
		m_UndoNetControlPoint = InputManager.instance.toolActionCollection.GetActionState("Undo Net Control Point", "ObjectToolSystem");
		m_DowngradeNetEdge = InputManager.instance.toolActionCollection.GetActionState("Downgrade Net Edge", "ObjectToolSystem");
		m_UpgradeNetEdge = InputManager.instance.toolActionCollection.GetActionState("Upgrade Net Edge", "ObjectToolSystem");
		m_DiscardUpgrade = InputManager.instance.toolActionCollection.GetActionState("Discard Upgrade", "ObjectToolSystem");
		m_DiscardDowngrade = InputManager.instance.toolActionCollection.GetActionState("Discard Downgrade", "ObjectToolSystem");
		m_ReplaceNetEdge = InputManager.instance.toolActionCollection.GetActionState("Replace Net Edge", "ObjectToolSystem");
		base.brushSize = 200f;
		base.brushAngle = 0f;
		base.brushStrength = 0.5f;
		distance = 3f;
		distanceScale = 1f;
		selectedSnap &= ~(Snap.AutoParent | Snap.ContourLines);
		ageMask = AgeMask.Sapling;
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
		m_SubSnapPoints.Dispose();
		m_UpgradeStates.Dispose();
		m_Rotation.Dispose();
		m_AppliedUpgrade.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		base.brushType = FindDefaultBrush(m_BrushQuery);
		base.brushSize = 200f;
		base.brushAngle = 0f;
		base.brushStrength = 0.5f;
		distance = 3f;
		distanceScale = 1f;
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		base.OnStartRunning();
		m_ControlPoints.Clear();
		m_SubSnapPoints.Clear();
		m_UpgradeStates.Clear();
		m_AppliedUpgrade.Value = default(NetToolSystem.AppliedUpgrade);
		m_LastRaycastPoint = default(ControlPoint);
		m_StartPoint = default(ControlPoint);
		m_State = State.Default;
		m_MovingInitialized = Entity.Null;
		m_ForceCancel = false;
		m_ApplyBlocked = false;
		Randomize();
		base.requireZones = false;
		base.requireUnderground = false;
		base.requireNetArrows = false;
		base.requireAreas = AreaTypeMask.Lots;
		base.requireNet = Layer.None;
		if (m_ToolSystem.actionMode.IsEditor())
		{
			base.requireAreas |= AreaTypeMask.Spaces;
		}
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		m_UpgradingObject = Entity.Null;
		if (this.mode == Mode.Upgrade && !base.EntityManager.HasBuffer<InstalledUpgrade>(GetUpgradable(m_ToolSystem.selected)))
		{
			this.mode = Mode.Create;
		}
		Mode mode = actualMode;
		if (mode == Mode.Brush && base.brushType == null)
		{
			base.brushType = FindDefaultBrush(m_BrushQuery);
		}
		if (mode != m_LastActualMode)
		{
			if (mode != Mode.Move)
			{
				m_MovingObject = Entity.Null;
			}
			if (m_LastActualMode == Mode.Brush)
			{
				m_ControlPoints.Clear();
			}
			bool flag = mode == Mode.Create || mode == Mode.Line || mode == Mode.Curve;
			if (m_UpgradeStates.Length != 0)
			{
				if (!flag)
				{
					m_ControlPoints.Clear();
					m_UpgradeStates.Clear();
					m_AppliedUpgrade.Value = default(NetToolSystem.AppliedUpgrade);
				}
			}
			else
			{
				int maxControlPointCount = GetMaxControlPointCount(mode);
				if (maxControlPointCount < m_ControlPoints.Length)
				{
					m_ControlPoints.RemoveRange(maxControlPointCount, m_ControlPoints.Length - maxControlPointCount);
				}
			}
			m_LastActualMode = mode;
		}
		bool flag2 = m_ForceCancel;
		m_ForceCancel = false;
		if (m_CameraController == null && CameraController.TryGet(out var cameraController))
		{
			m_CameraController = cameraController;
		}
		UpdateActions();
		if (m_Prefab != null)
		{
			allowUnderground = false;
			base.requireUnderground = false;
			base.requireNet = Layer.None;
			base.requireNetArrows = false;
			base.requireStops = TransportType.None;
			UpdateInfoview(m_ToolSystem.actionMode.IsEditor() ? Entity.Null : m_PrefabSystem.GetEntity(m_Prefab));
			GetAvailableSnapMask(out m_SnapOnMask, out m_SnapOffMask);
			m_PrefabSystem.TryGetComponentData<ObjectGeometryData>(m_Prefab, out var component);
			if (m_PrefabSystem.TryGetComponentData<PlaceableObjectData>(m_Prefab, out var component2))
			{
				if ((component2.m_Flags & Game.Objects.PlacementFlags.HasUndergroundElements) != Game.Objects.PlacementFlags.None)
				{
					base.requireNet |= Layer.Road;
				}
				if ((component2.m_Flags & (Game.Objects.PlacementFlags.Shoreline | Game.Objects.PlacementFlags.Floating)) != Game.Objects.PlacementFlags.None)
				{
					base.requireNet |= Layer.Waterway;
				}
			}
			switch (mode)
			{
			case Mode.Upgrade:
				if (m_PrefabSystem.HasComponent<ServiceUpgradeData>(m_Prefab))
				{
					m_UpgradingObject = GetUpgradable(m_ToolSystem.selected);
				}
				break;
			case Mode.Move:
				if (!base.EntityManager.Exists(m_MovingObject))
				{
					m_MovingObject = Entity.Null;
				}
				if (m_MovingInitialized != m_MovingObject)
				{
					m_MovingInitialized = m_MovingObject;
					InitializeRotation(m_MovingObject, component2);
				}
				break;
			}
			if ((ToolBaseSystem.GetActualSnap(selectedSnap, m_SnapOnMask, m_SnapOffMask) & (Snap.NetArea | Snap.NetNode | Snap.ObjectSurface)) != Snap.None && !m_PrefabSystem.HasComponent<BuildingData>(m_Prefab) && component2.m_SubReplacementType != SubReplacementType.Tree)
			{
				allowUnderground = true;
			}
			if (m_PrefabSystem.TryGetComponentData<TransportStopData>(m_Prefab, out var component3))
			{
				base.requireNetArrows = component3.m_TransportType != TransportType.Post;
				base.requireStops = component3.m_TransportType;
			}
			base.requireUnderground = allowUnderground && underground;
			base.requireZones = !base.requireUnderground && ((component2.m_Flags & Game.Objects.PlacementFlags.RoadSide) != Game.Objects.PlacementFlags.None || ((component.m_Flags & Game.Objects.GeometryFlags.OccupyZone) != Game.Objects.GeometryFlags.None && base.requireStops == TransportType.None));
			if (m_State != State.Default && !base.applyAction.enabled && !base.secondaryApplyAction.enabled)
			{
				m_State = State.Default;
			}
			if ((m_ToolRaycastSystem.raycastFlags & (RaycastFlags.DebugDisable | RaycastFlags.UIDisable)) == 0)
			{
				if (isUpgradeMode)
				{
					switch (m_State)
					{
					case State.Default:
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
					case State.Adding:
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
					case State.Removing:
						if (base.cancelAction.WasPressedThisFrame())
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
				if (base.cancelAction.WasPressedThisFrame())
				{
					if (mode == Mode.Upgrade && (m_SnapOnMask & ~m_SnapOffMask & Snap.OwnerSide) != Snap.None)
					{
						m_ToolSystem.activeTool = m_DefaultToolSystem;
					}
					return Cancel(inputDeps, base.cancelAction.WasReleasedThisFrame());
				}
				if (m_State == State.Adding || m_State == State.Removing)
				{
					if (base.applyAction.WasPressedThisFrame() || base.applyAction.WasReleasedThisFrame())
					{
						return Apply(inputDeps);
					}
					if (flag2 || base.secondaryApplyAction.WasPressedThisFrame() || base.secondaryApplyAction.WasReleasedThisFrame())
					{
						return Cancel(inputDeps);
					}
					return Update(inputDeps, fullUpdate: false);
				}
				if (m_State == State.Rotating && base.secondaryApplyAction.WasReleasedThisFrame())
				{
					if (m_RotationModified)
					{
						m_RotationModified = false;
					}
					else
					{
						Rotate(MathF.PI / 4f, fromStart: false, align: true);
					}
					m_State = State.Default;
					return Update(inputDeps, fullUpdate: false);
				}
				if ((mode == Mode.Curve || mode == Mode.Line) && m_State == State.Default && base.secondaryApplyAction.WasPressedThisFrame())
				{
					if (m_ControlPoints.Length <= 1)
					{
						return Cancel(inputDeps, base.secondaryApplyAction.WasReleasedThisFrame());
					}
					Rotate(MathF.PI / 4f, fromStart: false, align: true);
					for (int i = 0; i < m_ControlPoints.Length; i++)
					{
						ControlPoint value = m_ControlPoints[i];
						value.m_Rotation = m_Rotation.Value.m_Rotation;
						m_ControlPoints[i] = value;
					}
					return Update(inputDeps, fullUpdate: true);
				}
				if ((mode != Mode.Upgrade || (m_SnapOnMask & ~m_SnapOffMask & Snap.OwnerSide) == 0) && base.secondaryApplyAction.WasPressedThisFrame())
				{
					return Cancel(inputDeps, base.secondaryApplyAction.WasReleasedThisFrame());
				}
				if (base.applyAction.WasPressedThisFrame())
				{
					JobHandle result = Apply(inputDeps, base.applyAction.WasReleasedThisFrame());
					if (base.applyMode == ApplyMode.Apply && mode == Mode.Move)
					{
						if (m_ToolSystem.activeTool == this)
						{
							m_ToolSystem.activeTool = m_DefaultToolSystem;
						}
						m_TerrainSystem.OnBuildingMoved(m_MovingObject);
					}
					return result;
				}
				if (m_PreciseRotation.IsInProgress())
				{
					if (m_State == State.Default)
					{
						float num = m_PreciseRotation.ReadValue<float>();
						float angle = MathF.PI / 2f * num * UnityEngine.Time.deltaTime;
						Rotate(angle, fromStart: false, align: false);
						for (int j = 0; j < m_ControlPoints.Length; j++)
						{
							ControlPoint value2 = m_ControlPoints[j];
							value2.m_Rotation = m_Rotation.Value.m_Rotation;
							m_ControlPoints[j] = value2;
						}
					}
					return Update(inputDeps, fullUpdate: true);
				}
				if (m_State == State.Rotating && InputManager.instance.activeControlScheme == InputManager.ControlScheme.KeyboardAndMouse)
				{
					float3 @float = InputManager.instance.mousePosition;
					if (@float.x != m_RotationStartPosition.x)
					{
						float angle2 = (@float.x - m_RotationStartPosition.x) * (MathF.PI * 2f) * 0.002f;
						Rotate(angle2, fromStart: true, align: false);
						m_RotationModified = true;
					}
					return Update(inputDeps, fullUpdate: false);
				}
				return Update(inputDeps, fullUpdate: false);
			}
		}
		else
		{
			base.requireUnderground = false;
			base.requireZones = false;
			base.requireNetArrows = false;
			base.requireNet = Layer.None;
			UpdateInfoview(Entity.Null);
		}
		if (m_State == State.Adding && (base.applyAction.WasReleasedThisFrame() || base.cancelAction.WasPressedThisFrame()))
		{
			m_State = State.Default;
		}
		else if (m_State == State.Removing && (base.secondaryApplyAction.WasReleasedThisFrame() || base.cancelAction.WasPressedThisFrame()))
		{
			m_State = State.Default;
		}
		else if (m_State != State.Default && (base.applyAction.WasReleasedThisFrame() || base.secondaryApplyAction.WasReleasedThisFrame()))
		{
			m_State = State.Default;
		}
		return Clear(inputDeps);
	}
```

- `private Randomize() : System.Void`  

```csharp
private void Randomize()
	{
		m_RandomSeed = RandomSeed.Next();
		if (!(m_SelectedPrefab != null) || !m_PrefabSystem.TryGetComponentData<PlaceableObjectData>(m_SelectedPrefab, out var component) || component.m_RotationSymmetry == RotationSymmetry.None)
		{
			return;
		}
		Unity.Mathematics.Random random = m_RandomSeed.GetRandom(567890109);
		Rotation value = m_Rotation.Value;
		float num = MathF.PI * 2f;
		if (component.m_RotationSymmetry == RotationSymmetry.Any)
		{
			num = random.NextFloat(num);
			value.m_IsAligned = false;
		}
		else
		{
			num *= (float)random.NextInt((int)component.m_RotationSymmetry) / (float)(int)component.m_RotationSymmetry;
		}
		if ((component.m_Flags & Game.Objects.PlacementFlags.Wall) != Game.Objects.PlacementFlags.None)
		{
			value.m_Rotation = math.normalizesafe(math.mul(value.m_Rotation, quaternion.RotateZ(num)), quaternion.identity);
			if (value.m_IsAligned)
			{
				SnapJob.AlignRotation(ref value.m_Rotation, value.m_ParentRotation, zAxis: true);
			}
		}
		else
		{
			value.m_Rotation = math.normalizesafe(math.mul(value.m_Rotation, quaternion.RotateY(num)), quaternion.identity);
			if (value.m_IsAligned)
			{
				SnapJob.AlignRotation(ref value.m_Rotation, value.m_ParentRotation, zAxis: false);
			}
		}
		m_Rotation.Value = value;
	}
```

- `private virtual ResetActions() : System.Void`  

```csharp
private protected override void ResetActions()
	{
		base.ResetActions();
		m_PreciseRotation.enabled = false;
	}
```

- `private Rotate(System.Single angle, System.Boolean fromStart, System.Boolean align) : System.Void`  

```csharp
private void Rotate(float angle, bool fromStart, bool align)
	{
		m_PrefabSystem.TryGetComponentData<PlaceableObjectData>(m_Prefab, out var component);
		Rotation value = m_Rotation.Value;
		bool flag = (component.m_Flags & Game.Objects.PlacementFlags.Wall) != 0;
		value.m_Rotation = math.mul(fromStart ? m_StartRotation : value.m_Rotation, flag ? quaternion.RotateZ(angle) : quaternion.RotateY(angle));
		value.m_Rotation = math.normalizesafe(value.m_Rotation, quaternion.identity);
		if (align)
		{
			quaternion parentRotation = value.m_ParentRotation;
			if ((actualMode == Mode.Line || actualMode == Mode.Curve) && m_UpgradeStates.Length == 0 && m_ControlPoints.Length >= 2)
			{
				float2 value2 = m_ControlPoints[1].m_Position.xz - m_ControlPoints[0].m_Position.xz;
				if (MathUtils.TryNormalize(ref value2))
				{
					parentRotation = quaternion.LookRotation(new float3(value2.x, 0f, value2.y), math.up());
				}
			}
			SnapJob.AlignRotation(ref value.m_Rotation, parentRotation, flag);
		}
		value.m_IsAligned = align;
		m_Rotation.Value = value;
	}
```

- `private SetAppliedUpgrade(System.Boolean removing) : System.Void`  

```csharp
private void SetAppliedUpgrade(bool removing)
	{
		m_AppliedUpgrade.Value = default(NetToolSystem.AppliedUpgrade);
		if (m_UpgradeStates.Length < 1 || m_ControlPoints.Length < 4)
		{
			return;
		}
		Entity originalEntity = m_ControlPoints[m_ControlPoints.Length - 3].m_OriginalEntity;
		Entity originalEntity2 = m_ControlPoints[m_ControlPoints.Length - 2].m_OriginalEntity;
		NetToolSystem.UpgradeState upgradeState = m_UpgradeStates[m_UpgradeStates.Length - 1];
		NetToolSystem.AppliedUpgrade value = new NetToolSystem.AppliedUpgrade
		{
			m_SubReplacementPrefab = upgradeState.m_SubReplacementPrefab,
			m_Flags = (removing ? upgradeState.m_RemoveFlags : upgradeState.m_AddFlags),
			m_SubReplacementType = upgradeState.m_SubReplacementType,
			m_SubReplacementSide = upgradeState.m_SubReplacementSide
		};
		if (originalEntity == originalEntity2)
		{
			value.m_Entity = originalEntity;
			m_AppliedUpgrade.Value = value;
		}
		else
		{
			if (!base.EntityManager.TryGetBuffer(originalEntity, isReadOnly: true, out DynamicBuffer<ConnectedEdge> buffer))
			{
				return;
			}
			for (int i = 0; i < buffer.Length; i++)
			{
				Entity edge = buffer[i].m_Edge;
				if (base.EntityManager.TryGetComponent<Edge>(edge, out var component) && ((component.m_Start == originalEntity && component.m_End == originalEntity2) || (component.m_End == originalEntity && component.m_Start == originalEntity2)))
				{
					value.m_Entity = edge;
					m_AppliedUpgrade.Value = value;
				}
			}
		}
	}
```

- `public virtual SetUnderground(System.Boolean underground) : System.Void`  

```csharp
public override void SetUnderground(bool underground)
	{
		this.underground = underground;
	}
```

- `private SnapControlPoint(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle SnapControlPoint(JobHandle inputDeps)
	{
		Entity selected = ((actualMode == Mode.Move) ? m_MovingObject : GetUpgradable(m_ToolSystem.selected));
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle dependencies3;
		JobHandle deps;
		JobHandle jobHandle = IJobExtensions.Schedule(new SnapJob
		{
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_RemoveUpgrade = (m_State == State.Removing),
			m_LeftHandTraffic = m_CityConfigurationSystem.leftHandTraffic,
			m_Distance = math.max(1f, distance),
			m_DistanceScale = distanceScale,
			m_Snap = GetActualSnap(),
			m_Mode = actualMode,
			m_Prefab = m_PrefabSystem.GetEntity(m_Prefab),
			m_Selected = selected,
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AttachedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TerrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Terrain_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LocalTransformCacheData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_LocalTransformCache_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OrphanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Orphan_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StartNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EndNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UpgradedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Upgraded_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingExtensionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingExtensionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoadCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RoadComposition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlaceableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MovingObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MovingObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AssetStampData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AssetStampData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_OutsideConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransportStopData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportStopData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StackData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUpgradeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ServiceUpgradeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RoadData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubReplacements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubReplacement_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabCompositionAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_ObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies),
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies2),
			m_ZoneSearchTree = m_ZoneSearchSystem.GetSearchTree(readOnly: true, out dependencies3),
			m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_ControlPoints = m_ControlPoints,
			m_SubSnapPoints = m_SubSnapPoints,
			m_UpgradeStates = m_UpgradeStates,
			m_Rotation = m_Rotation,
			m_AppliedUpgrade = m_AppliedUpgrade
		}, JobUtils.CombineDependencies(inputDeps, dependencies, dependencies2, dependencies3, deps));
		m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle);
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		m_ZoneSearchSystem.AddSearchTreeReader(jobHandle);
		m_WaterSystem.AddSurfaceReader(jobHandle);
		return jobHandle;
	}
```

- `public StartMoving(Unity.Entities.Entity movingObject) : System.Void`  

```csharp
public void StartMoving(Entity movingObject)
	{
		m_MovingObject = movingObject;
		if (m_ToolSystem.actionMode.IsEditor() && base.EntityManager.HasComponent<Game.Buildings.ServiceUpgrade>(m_MovingObject) && base.EntityManager.TryGetComponent<Owner>(m_MovingObject, out var component))
		{
			m_MovingObject = component.m_Owner;
		}
		m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_RelocateBuildingSound);
		mode = Mode.Move;
		prefab = m_PrefabSystem.GetPrefab<ObjectPrefab>(base.EntityManager.GetComponentData<PrefabRef>(m_MovingObject));
	}
```

- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public override bool TrySetPrefab(PrefabBase prefab)
	{
		if (prefab is ObjectPrefab objectPrefab)
		{
			Mode mode = this.mode;
			if (!m_ToolSystem.actionMode.IsEditor() && prefab.Has<Game.Prefabs.ServiceUpgrade>())
			{
				Entity entity = m_PrefabSystem.GetEntity(prefab);
				if (!InternalCompilerInterface.HasComponentAfterCompletingDependency(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RO_ComponentLookup, ref base.CheckedStateRef, entity))
				{
					return false;
				}
				mode = Mode.Upgrade;
			}
			else if (mode == Mode.Upgrade || mode == Mode.Move)
			{
				mode = Mode.Create;
			}
			this.prefab = objectPrefab;
			this.mode = mode;
			return true;
		}
		if (prefab is TransformPrefab transformPrefab)
		{
			transform = transformPrefab;
			this.mode = Mode.Create;
			return true;
		}
		return false;
	}
```

- `private Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Update(JobHandle inputDeps, bool fullUpdate)
	{
		if (actualMode == Mode.Brush)
		{
			if (GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate))
			{
				if (m_State != State.Default)
				{
					base.applyMode = (GetAllowApply() ? ApplyMode.Apply : ApplyMode.Clear);
					Randomize();
					m_StartPoint = m_LastRaycastPoint;
					m_LastRaycastPoint = controlPoint;
					return UpdateDefinitions(inputDeps);
				}
				if (m_LastRaycastPoint.Equals(controlPoint) && !forceUpdate)
				{
					if (HaveBrushSettingsChanged())
					{
						base.applyMode = ApplyMode.Clear;
						return UpdateDefinitions(inputDeps);
					}
					base.applyMode = ApplyMode.None;
					return inputDeps;
				}
				base.applyMode = ApplyMode.Clear;
				m_StartPoint = controlPoint;
				m_LastRaycastPoint = controlPoint;
				return UpdateDefinitions(inputDeps);
			}
			if (m_LastRaycastPoint.Equals(default(ControlPoint)) && !forceUpdate)
			{
				base.applyMode = ApplyMode.None;
				return inputDeps;
			}
			if (m_State != State.Default)
			{
				base.applyMode = (GetAllowApply() ? ApplyMode.Apply : ApplyMode.Clear);
				Randomize();
				m_StartPoint = m_LastRaycastPoint;
				m_LastRaycastPoint = default(ControlPoint);
			}
			else
			{
				base.applyMode = ApplyMode.Clear;
				m_StartPoint = default(ControlPoint);
				m_LastRaycastPoint = default(ControlPoint);
			}
			return UpdateDefinitions(inputDeps);
		}
		if (GetRaycastResult(out ControlPoint controlPoint2, out bool forceUpdate2))
		{
			controlPoint2.m_Rotation = m_Rotation.Value.m_Rotation;
			forceUpdate2 = forceUpdate2 || fullUpdate;
			base.applyMode = ApplyMode.None;
			if (!m_LastRaycastPoint.Equals(controlPoint2) || forceUpdate2)
			{
				m_LastRaycastPoint = controlPoint2;
				ControlPoint controlPoint3 = default(ControlPoint);
				if (m_ControlPoints.Length != 0)
				{
					controlPoint3 = m_ControlPoints[m_ControlPoints.Length - 1];
				}
				if (m_State == State.Adding || m_State == State.Removing)
				{
					if (m_ControlPoints.Length == 1)
					{
						m_ControlPoints.Add(in controlPoint2);
					}
					else
					{
						m_ControlPoints[m_ControlPoints.Length - 1] = controlPoint2;
					}
				}
				else
				{
					if (m_UpgradeStates.Length != 0)
					{
						m_ControlPoints.Clear();
						m_UpgradeStates.Clear();
					}
					if (m_ControlPoints.Length == 0)
					{
						m_ControlPoints.Add(in controlPoint2);
					}
					else
					{
						m_ControlPoints[m_ControlPoints.Length - 1] = controlPoint2;
					}
				}
				inputDeps = SnapControlPoint(inputDeps);
				JobHandle.ScheduleBatchedJobs();
				if (!forceUpdate2)
				{
					inputDeps.Complete();
					ControlPoint other = m_ControlPoints[m_ControlPoints.Length - 1];
					forceUpdate2 = !controlPoint3.EqualsIgnoreHit(other);
				}
				if (forceUpdate2)
				{
					base.applyMode = ApplyMode.Clear;
					inputDeps = UpdateDefinitions(inputDeps);
				}
			}
		}
		else
		{
			base.applyMode = ApplyMode.Clear;
			m_LastRaycastPoint = default(ControlPoint);
			if (m_State == State.Default)
			{
				m_ControlPoints.Clear();
				m_UpgradeStates.Clear();
				m_AppliedUpgrade.Value = default(NetToolSystem.AppliedUpgrade);
			}
			inputDeps = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
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
			if (isUpgradeMode)
			{
				if (m_State == State.Default || m_UpgradeStates.Length == 1)
				{
					bool replacementExist = false;
					base.applyAction.enabled = base.actionsEnabled && GetAllowUpgrade(out replacementExist);
					base.applyActionOverride = (replacementExist ? m_ReplaceNetEdge : m_UpgradeNetEdge);
					base.secondaryApplyAction.enabled = base.actionsEnabled && GetAllowDowngrade(out var _);
					base.secondaryApplyActionOverride = m_DowngradeNetEdge;
					base.cancelAction.enabled = false;
					base.cancelActionOverride = null;
					m_PreciseRotation.enabled = false;
				}
				else if (m_State == State.Adding)
				{
					base.applyAction.enabled = base.actionsEnabled;
					base.applyActionOverride = m_UpgradeNetEdge;
					base.secondaryApplyAction.enabled = false;
					base.secondaryApplyActionOverride = null;
					base.cancelAction.enabled = base.actionsEnabled;
					base.cancelActionOverride = m_DiscardUpgrade;
					m_PreciseRotation.enabled = false;
				}
				else if (m_State == State.Removing)
				{
					base.applyAction.enabled = false;
					base.applyActionOverride = null;
					base.secondaryApplyAction.enabled = base.actionsEnabled;
					base.secondaryApplyActionOverride = m_DowngradeNetEdge;
					base.cancelAction.enabled = base.actionsEnabled;
					base.cancelActionOverride = m_DiscardDowngrade;
					m_PreciseRotation.enabled = false;
				}
				return;
			}
			switch (actualMode)
			{
			case Mode.Create:
				base.applyAction.enabled = base.actionsEnabled && GetAllowApply();
				base.applyActionOverride = m_PlaceObject;
				base.secondaryApplyAction.enabled = base.actionsEnabled && GetAllowRotation();
				base.secondaryApplyActionOverride = m_RotateObject;
				base.cancelAction.enabled = false;
				base.cancelActionOverride = null;
				m_PreciseRotation.enabled = base.actionsEnabled && GetAllowPreciseRotation();
				break;
			case Mode.Upgrade:
				base.applyAction.enabled = base.actionsEnabled && GetAllowApply();
				base.applyActionOverride = m_PlaceUpgrade;
				base.secondaryApplyAction.enabled = base.actionsEnabled && GetAllowRotation();
				base.secondaryApplyActionOverride = m_RotateObject;
				base.cancelAction.enabled = base.actionsEnabled;
				base.cancelActionOverride = m_MouseCancel;
				m_PreciseRotation.enabled = base.actionsEnabled && GetAllowPreciseRotation();
				break;
			case Mode.Move:
				base.applyAction.enabled = base.actionsEnabled && GetAllowApply();
				base.applyActionOverride = m_MoveObject;
				base.secondaryApplyAction.enabled = base.actionsEnabled && GetAllowRotation();
				base.secondaryApplyActionOverride = m_RotateObject;
				base.cancelAction.enabled = false;
				base.cancelActionOverride = null;
				m_PreciseRotation.enabled = base.actionsEnabled && GetAllowPreciseRotation();
				break;
			case Mode.Brush:
			{
				IProxyAction proxyAction = base.applyAction;
				bool replacementExist2 = base.actionsEnabled;
				if (replacementExist2)
				{
					replacementExist2 = m_State switch
					{
						State.Default => GetAllowApply(), 
						State.Adding => true, 
						_ => false, 
					};
				}
				proxyAction.enabled = replacementExist2;
				base.applyActionOverride = m_PaintObject;
				proxyAction = base.secondaryApplyAction;
				replacementExist2 = base.actionsEnabled;
				if (replacementExist2)
				{
					replacementExist2 = m_State switch
					{
						State.Default => GetAllowApply(), 
						State.Removing => true, 
						_ => false, 
					};
				}
				proxyAction.enabled = replacementExist2;
				base.secondaryApplyActionOverride = m_EraseObject;
				base.cancelAction.enabled = false;
				base.cancelActionOverride = null;
				m_PreciseRotation.enabled = false;
				break;
			}
			case Mode.Stamp:
				base.applyAction.enabled = base.actionsEnabled && (GetAllowApply() || m_State != State.Default);
				base.applyActionOverride = m_PlaceObject;
				base.secondaryApplyAction.enabled = base.actionsEnabled && GetAllowRotation();
				base.secondaryApplyActionOverride = m_RotateObject;
				base.cancelAction.enabled = false;
				base.cancelActionOverride = null;
				m_PreciseRotation.enabled = base.actionsEnabled && GetAllowPreciseRotation();
				break;
			case Mode.Line:
			case Mode.Curve:
				base.applyAction.enabled = base.actionsEnabled && GetAllowApply();
				base.applyActionOverride = ((m_ControlPoints.Length < GetMaxControlPointCount(actualMode)) ? m_PlaceNetControlPoint : m_PlaceNetEdge);
				base.secondaryApplyAction.enabled = base.actionsEnabled && GetAllowRotation() && (InputManager.instance.isGamepadControlSchemeActive || m_ControlPoints.Length <= 1);
				base.secondaryApplyActionOverride = m_RotateObject;
				base.cancelAction.enabled = base.actionsEnabled && m_ControlPoints.Length >= 2;
				base.cancelActionOverride = m_UndoNetControlPoint;
				m_PreciseRotation.enabled = base.actionsEnabled && allowRotation && GetAllowPreciseRotation();
				break;
			}
		}
	}
```

- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateDefinitions(JobHandle inputDeps)
	{
		JobHandle jobHandle = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
		if (m_Prefab != null)
		{
			Snap actualSnap = GetActualSnap();
			Entity entity = m_PrefabSystem.GetEntity(m_Prefab);
			if (actualMode != Mode.Brush && (actualSnap & Snap.NetArea) != Snap.None)
			{
				if (m_State == State.Adding || m_State == State.Removing)
				{
					return JobHandle.CombineDependencies(jobHandle, UpdateSubReplacementDefinitions(inputDeps));
				}
				if (base.EntityManager.TryGetComponent<PlaceableObjectData>(entity, out var component) && component.m_SubReplacementType != SubReplacementType.None)
				{
					inputDeps.Complete();
					if (m_UpgradeStates.Length != 0)
					{
						return JobHandle.CombineDependencies(jobHandle, UpdateSubReplacementDefinitions(default(JobHandle)));
					}
				}
			}
			Entity laneContainer = Entity.Null;
			Entity transformPrefab = Entity.Null;
			Entity brushPrefab = Entity.Null;
			float deltaTime = UnityEngine.Time.deltaTime;
			float num = 0f;
			if (m_ToolSystem.actionMode.IsEditor())
			{
				GetContainers(m_ContainerQuery, out laneContainer, out var _);
			}
			if (m_TransformPrefab != null)
			{
				transformPrefab = m_PrefabSystem.GetEntity(m_TransformPrefab);
			}
			if (actualMode == Mode.Brush && base.brushType != null)
			{
				brushPrefab = m_PrefabSystem.GetEntity(base.brushType);
				EnsureCachedBrushData();
				ControlPoint value = m_StartPoint;
				ControlPoint value2 = m_LastRaycastPoint;
				value.m_OriginalEntity = Entity.Null;
				value2.m_OriginalEntity = Entity.Null;
				m_ControlPoints.Clear();
				m_UpgradeStates.Clear();
				m_AppliedUpgrade.Value = default(NetToolSystem.AppliedUpgrade);
				m_ControlPoints.Add(in value);
				m_ControlPoints.Add(in value2);
				if (m_State == State.Default)
				{
					deltaTime = 0.1f;
				}
			}
			if (actualMode == Mode.Line || actualMode == Mode.Curve)
			{
				num = math.max(1f, distance) * distanceScale;
			}
			NativeReference<AttachmentData> attachmentPrefab = default(NativeReference<AttachmentData>);
			if (!m_ToolSystem.actionMode.IsEditor() && base.EntityManager.TryGetComponent<PlaceholderBuildingData>(entity, out var component2))
			{
				ZoneData componentData = base.EntityManager.GetComponentData<ZoneData>(component2.m_ZonePrefab);
				BuildingData componentData2 = base.EntityManager.GetComponentData<BuildingData>(entity);
				m_BuildingQuery.ResetFilter();
				m_BuildingQuery.SetSharedComponentFilter(new BuildingSpawnGroupData(componentData.m_ZoneType));
				attachmentPrefab = new NativeReference<AttachmentData>(Allocator.TempJob);
				JobHandle outJobHandle;
				NativeList<ArchetypeChunk> chunks = m_BuildingQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
				inputDeps = IJobExtensions.Schedule(new FindAttachmentBuildingJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_BuildingDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_SpawnableBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_BuildingData = componentData2,
					m_RandomSeed = m_RandomSeed,
					m_Chunks = chunks,
					m_AttachmentPrefab = attachmentPrefab
				}, JobHandle.CombineDependencies(inputDeps, outJobHandle));
				chunks.Dispose(inputDeps);
			}
			jobHandle = JobHandle.CombineDependencies(jobHandle, CreateDefinitions(entity, transformPrefab, brushPrefab, m_UpgradingObject, m_MovingObject, laneContainer, m_CityConfigurationSystem.defaultTheme, m_ControlPoints, attachmentPrefab, m_ToolSystem.actionMode.IsEditor(), m_CityConfigurationSystem.leftHandTraffic, m_State == State.Removing, actualMode == Mode.Stamp, base.brushSize, math.radians(base.brushAngle), base.brushStrength, num, deltaTime, m_RandomSeed, actualSnap, actualAgeMask, inputDeps));
			if (attachmentPrefab.IsCreated)
			{
				attachmentPrefab.Dispose(jobHandle);
			}
		}
		return jobHandle;
	}
```

- `private UpdateSubReplacementDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateSubReplacementDefinitions(JobHandle inputDeps)
	{
		JobHandle deps;
		JobHandle jobHandle = IJobExtensions.Schedule(new NetToolSystem.CreateDefinitionsJob
		{
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_RemoveUpgrade = (m_State == State.Removing),
			m_LefthandTraffic = m_CityConfigurationSystem.leftHandTraffic,
			m_Mode = NetToolSystem.Mode.Replace,
			m_RandomSeed = m_RandomSeed,
			m_AgeMask = actualAgeMask,
			m_ControlPoints = m_ControlPoints,
			m_UpgradeStates = m_UpgradeStates,
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UpgradedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Upgraded_RO_ComponentLookup, ref base.CheckedStateRef),
			m_FixedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Fixed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EditorContainerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LocalTransformCacheData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_LocalTransformCache_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AttachmentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attachment_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ExtensionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Extension_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlaceableData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableNetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSpawnableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabAreaGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubReplacements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubReplacement_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_CachedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Tools_LocalNodeCache_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubAreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubAreaNode_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabPlaceholderElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_NetPrefab = m_PrefabSystem.GetEntity(m_Prefab),
			m_WaterSurfaceData = m_WaterSystem.GetVelocitiesSurfaceData(out deps),
			m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer()
		}, JobHandle.CombineDependencies(inputDeps, deps));
		m_WaterSystem.AddVelocitySurfaceReader(jobHandle);
		m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle);
		return jobHandle;
	}
```


## Nested types

- `Game.Tools.ObjectToolSystem+Mode`  
- `Game.Tools.ObjectToolSystem+State`  
- `Game.Tools.ObjectToolSystem+Rotation`  
- `Game.Tools.ObjectToolSystem+SnapJob`  
- `Game.Tools.ObjectToolSystem+FindAttachmentBuildingJob`  
- `Game.Tools.ObjectToolSystem+TypeHandle`  
- `Game.Tools.ObjectToolSystem+<get_toolActions>d__106`  

