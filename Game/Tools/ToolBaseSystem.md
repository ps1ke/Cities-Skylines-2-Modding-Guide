# Game.Tools.ToolBaseSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class abstract public  

**Base:** `Game.GameSystemBase`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public abstract class ToolBaseSystem : Game.GameSystemBase, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private UnityEngine.Color32 <color>k__BackingField;
    private Game.Prefabs.BrushPrefab <brushType>k__BackingField;
    private System.Single <brushSize>k__BackingField;
    private System.Single <brushAngle>k__BackingField;
    private System.Single <brushStrength>k__BackingField;
    private System.Boolean <requireZones>k__BackingField;
    private System.Boolean <requireUnderground>k__BackingField;
    private System.Boolean <requirePipelines>k__BackingField;
    private System.Boolean <requireNetArrows>k__BackingField;
    private System.Boolean <requireStopIcons>k__BackingField;
    private Game.Areas.AreaTypeMask <requireAreas>k__BackingField;
    private Game.Routes.RouteType <requireRoutes>k__BackingField;
    private Game.Prefabs.TransportType <requireStops>k__BackingField;
    private Game.Net.Layer <requireNet>k__BackingField;
    private Game.Prefabs.InfoviewPrefab <infoview>k__BackingField;
    private System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> <infomodes>k__BackingField;
    private Game.Tools.Snap <selectedSnap>k__BackingField;
    private Game.Tools.ApplyMode <applyMode>k__BackingField;
    private System.Boolean <allowUnderground>k__BackingField;
    protected Game.Tools.ToolSystem m_ToolSystem;
    protected Game.Prefabs.PrefabSystem m_PrefabSystem;
    protected Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    protected Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    protected Game.Tools.OriginalDeletedSystem m_OriginalDeletedSystem;
    protected Unity.Entities.EntityQuery m_ErrorQuery;
    protected Game.Tools.Snap m_SnapOnMask;
    protected Game.Tools.Snap m_SnapOffMask;
    protected System.Boolean m_HasFocus;
    protected System.Boolean m_FocusChanged;
    protected System.Boolean m_ForceUpdate;
    private Game.Input.IProxyAction m_ApplyAction;
    private Game.Input.IProxyAction m_SecondaryApplyAction;
    private Game.Input.IProxyAction m_CancelAction;
    private System.Boolean <actionsEnabled>k__BackingField;
    private Game.Tools.ToolBaseSystem+TypeHandle __TypeHandle;
    private static System.Action<Game.Input.ProxyAction> EventToolActionPerformed;
    public static const Game.Tools.Snap kSnapAllIgnoredMask;

    public System.String toolID { get; }
    public System.Int32 uiModeIndex { get; }
    public UnityEngine.Color32 color { get; set; }
    public Game.Prefabs.BrushPrefab brushType { get; set; }
    public System.Single brushSize { get; set; }
    public System.Single brushAngle { get; set; }
    public System.Single brushStrength { get; set; }
    public System.Boolean requireZones { get; protected set; }
    public System.Boolean requireUnderground { get; protected set; }
    public System.Boolean requirePipelines { get; protected set; }
    public System.Boolean requireNetArrows { get; protected set; }
    public System.Boolean requireStopIcons { get; protected set; }
    public Game.Areas.AreaTypeMask requireAreas { get; protected set; }
    public Game.Routes.RouteType requireRoutes { get; protected set; }
    public Game.Prefabs.TransportType requireStops { get; protected set; }
    public Game.Net.Layer requireNet { get; protected set; }
    public Game.Prefabs.InfoviewPrefab infoview { get; private set; }
    public System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> infomodes { get; private set; }
    public Game.Tools.Snap selectedSnap { get; set; }
    public Game.Tools.ApplyMode applyMode { get; protected set; }
    public System.Boolean allowUnderground { get; protected set; }
    public System.Boolean brushing { get; }
    protected Game.Input.IProxyAction applyAction { protected get; }
    protected Game.Input.IProxyAction secondaryApplyAction { protected get; }
    protected Game.Input.IProxyAction cancelAction { protected get; }
    protected Game.Input.IProxyAction applyActionOverride { protected get; protected set; }
    protected Game.Input.IProxyAction secondaryApplyActionOverride { protected get; protected set; }
    protected Game.Input.IProxyAction cancelActionOverride { protected get; protected set; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> baseToolActions { private get; }
    internal System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> actions { internal get; }
    private System.Boolean actionsEnabled { private get; private set; }

    protected ToolBaseSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected Unity.Jobs.JobHandle DestroyDefinitions(Unity.Entities.EntityQuery group, Game.Tools.ToolOutputBarrier barrier, Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void ElevationDown();
    public virtual System.Void ElevationScroll();
    public virtual System.Void ElevationUp();
    protected System.Void EnsureCachedBrushData();
    public System.Boolean Equals(Game.Tools.ToolBaseSystem other);
    protected Game.Prefabs.BrushPrefab FindDefaultBrush(Unity.Entities.EntityQuery query);
    public static Game.Tools.Snap GetActualSnap(Game.Tools.Snap selectedSnap, Game.Tools.Snap onMask, Game.Tools.Snap offMask);
    protected Game.Tools.Snap GetActualSnap();
    protected virtual System.Boolean GetAllowApply();
    public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    protected Unity.Entities.EntityQuery GetBrushQuery();
    protected Unity.Entities.EntityQuery GetContainerQuery();
    protected System.Boolean GetContainers(Unity.Entities.EntityQuery group, Unity.Entities.Entity& laneContainer, Unity.Entities.Entity& transformContainer);
    protected Unity.Entities.EntityQuery GetDefinitionQuery();
    public abstract Game.Prefabs.PrefabBase GetPrefab();
    protected System.Boolean GetRaycastResult(Unity.Entities.Entity& entity, Game.Common.RaycastHit& hit);
    protected System.Boolean GetRaycastResult(Unity.Entities.Entity& entity, Game.Common.RaycastHit& hit, System.Boolean& forceUpdate);
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint);
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate);
    public virtual System.Void GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes);
    public virtual System.Void InitializeRaycast();
    protected Unity.Jobs.JobHandle InvertBrushes(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps);
    private System.Void OnActionInteraction(Game.Input.ProxyAction action, UnityEngine.InputSystem.InputActionPhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnFocusChanged(System.Boolean hasfocus);
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnStopRunning();
    protected System.Void OnUpdate();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    private virtual System.Void ResetActions();
    protected System.Void SetAction(Game.Input.IProxyAction& action, Game.Input.IProxyAction newAction);
    private virtual System.Void SetActions();
    private System.Void SetInteraction(System.Boolean set);
    public virtual System.Void SetUnderground(System.Boolean underground);
    public System.Void ToggleToolOptions(System.Boolean enabled);
    public abstract System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private virtual System.Void UpdateActions();
    protected System.Void UpdateInfoview(Unity.Entities.Entity prefab);
}
```


## Fields

- `private UnityEngine.Color32 <color>k__BackingField`  

```csharp
private UnityEngine.Color32 <color>k__BackingField;
```

- `private Game.Prefabs.BrushPrefab <brushType>k__BackingField`  

```csharp
private Game.Prefabs.BrushPrefab <brushType>k__BackingField;
```

- `private System.Single <brushSize>k__BackingField`  

```csharp
private System.Single <brushSize>k__BackingField;
```

- `private System.Single <brushAngle>k__BackingField`  

```csharp
private System.Single <brushAngle>k__BackingField;
```

- `private System.Single <brushStrength>k__BackingField`  

```csharp
private System.Single <brushStrength>k__BackingField;
```

- `private System.Boolean <requireZones>k__BackingField`  

```csharp
private System.Boolean <requireZones>k__BackingField;
```

- `private System.Boolean <requireUnderground>k__BackingField`  

```csharp
private System.Boolean <requireUnderground>k__BackingField;
```

- `private System.Boolean <requirePipelines>k__BackingField`  

```csharp
private System.Boolean <requirePipelines>k__BackingField;
```

- `private System.Boolean <requireNetArrows>k__BackingField`  

```csharp
private System.Boolean <requireNetArrows>k__BackingField;
```

- `private System.Boolean <requireStopIcons>k__BackingField`  

```csharp
private System.Boolean <requireStopIcons>k__BackingField;
```

- `private Game.Areas.AreaTypeMask <requireAreas>k__BackingField`  

```csharp
private Game.Areas.AreaTypeMask <requireAreas>k__BackingField;
```

- `private Game.Routes.RouteType <requireRoutes>k__BackingField`  

```csharp
private Game.Routes.RouteType <requireRoutes>k__BackingField;
```

- `private Game.Prefabs.TransportType <requireStops>k__BackingField`  

```csharp
private Game.Prefabs.TransportType <requireStops>k__BackingField;
```

- `private Game.Net.Layer <requireNet>k__BackingField`  

```csharp
private Game.Net.Layer <requireNet>k__BackingField;
```

- `private Game.Prefabs.InfoviewPrefab <infoview>k__BackingField`  

```csharp
private Game.Prefabs.InfoviewPrefab <infoview>k__BackingField;
```

- `private System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> <infomodes>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> <infomodes>k__BackingField;
```

- `private Game.Tools.Snap <selectedSnap>k__BackingField`  

```csharp
private Game.Tools.Snap <selectedSnap>k__BackingField;
```

- `private Game.Tools.ApplyMode <applyMode>k__BackingField`  

```csharp
private Game.Tools.ApplyMode <applyMode>k__BackingField;
```

- `private System.Boolean <allowUnderground>k__BackingField`  

```csharp
private System.Boolean <allowUnderground>k__BackingField;
```

- `protected Game.Tools.ToolSystem m_ToolSystem`  

```csharp
protected Game.Tools.ToolSystem m_ToolSystem;
```

- `protected Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
protected Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `protected Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
protected Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `protected Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
protected Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `protected Game.Tools.OriginalDeletedSystem m_OriginalDeletedSystem`  

```csharp
protected Game.Tools.OriginalDeletedSystem m_OriginalDeletedSystem;
```

- `protected Unity.Entities.EntityQuery m_ErrorQuery`  

```csharp
protected Unity.Entities.EntityQuery m_ErrorQuery;
```

- `protected Game.Tools.Snap m_SnapOnMask`  

```csharp
protected Game.Tools.Snap m_SnapOnMask;
```

- `protected Game.Tools.Snap m_SnapOffMask`  

```csharp
protected Game.Tools.Snap m_SnapOffMask;
```

- `protected System.Boolean m_HasFocus`  

```csharp
protected System.Boolean m_HasFocus;
```

- `protected System.Boolean m_FocusChanged`  

```csharp
protected System.Boolean m_FocusChanged;
```

- `protected System.Boolean m_ForceUpdate`  

```csharp
protected System.Boolean m_ForceUpdate;
```

- `private Game.Input.IProxyAction m_ApplyAction`  

```csharp
private Game.Input.IProxyAction m_ApplyAction;
```

- `private Game.Input.IProxyAction m_SecondaryApplyAction`  

```csharp
private Game.Input.IProxyAction m_SecondaryApplyAction;
```

- `private Game.Input.IProxyAction m_CancelAction`  

```csharp
private Game.Input.IProxyAction m_CancelAction;
```

- `private System.Boolean <actionsEnabled>k__BackingField`  

```csharp
private System.Boolean <actionsEnabled>k__BackingField;
```

- `private Game.Tools.ToolBaseSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ToolBaseSystem+TypeHandle __TypeHandle;
```

- `private static System.Action<Game.Input.ProxyAction> EventToolActionPerformed`  

```csharp
private static System.Action<Game.Input.ProxyAction> EventToolActionPerformed;
```

- `public static const Game.Tools.Snap kSnapAllIgnoredMask`  

```csharp
public static const Game.Tools.Snap kSnapAllIgnoredMask;
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

- `public UnityEngine.Color32 color { get; set }`  

```csharp
public UnityEngine.Color32 color { get; set; }
```

- `public Game.Prefabs.BrushPrefab brushType { get; set }`  

```csharp
public Game.Prefabs.BrushPrefab brushType { get; set; }
```

- `public System.Single brushSize { get; set }`  

```csharp
public System.Single brushSize { get; set; }
```

- `public System.Single brushAngle { get; set }`  

```csharp
public System.Single brushAngle { get; set; }
```

- `public System.Single brushStrength { get; set }`  

```csharp
public System.Single brushStrength { get; set; }
```

- `public System.Boolean requireZones { get; protected set }`  

```csharp
public System.Boolean requireZones { get; protected set; }
```

- `public System.Boolean requireUnderground { get; protected set }`  

```csharp
public System.Boolean requireUnderground { get; protected set; }
```

- `public System.Boolean requirePipelines { get; protected set }`  

```csharp
public System.Boolean requirePipelines { get; protected set; }
```

- `public System.Boolean requireNetArrows { get; protected set }`  

```csharp
public System.Boolean requireNetArrows { get; protected set; }
```

- `public System.Boolean requireStopIcons { get; protected set }`  

```csharp
public System.Boolean requireStopIcons { get; protected set; }
```

- `public Game.Areas.AreaTypeMask requireAreas { get; protected set }`  

```csharp
public Game.Areas.AreaTypeMask requireAreas { get; protected set; }
```

- `public Game.Routes.RouteType requireRoutes { get; protected set }`  

```csharp
public Game.Routes.RouteType requireRoutes { get; protected set; }
```

- `public Game.Prefabs.TransportType requireStops { get; protected set }`  

```csharp
public Game.Prefabs.TransportType requireStops { get; protected set; }
```

- `public Game.Net.Layer requireNet { get; protected set }`  

```csharp
public Game.Net.Layer requireNet { get; protected set; }
```

- `public Game.Prefabs.InfoviewPrefab infoview { get; private set }`  

```csharp
public Game.Prefabs.InfoviewPrefab infoview { get; private set; }
```

- `public System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> infomodes { get; private set }`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> infomodes { get; private set; }
```

- `public Game.Tools.Snap selectedSnap { get; set }`  

```csharp
public Game.Tools.Snap selectedSnap { get; set; }
```

- `public Game.Tools.ApplyMode applyMode { get; protected set }`  

```csharp
public Game.Tools.ApplyMode applyMode { get; protected set; }
```

- `public System.Boolean allowUnderground { get; protected set }`  

```csharp
public System.Boolean allowUnderground { get; protected set; }
```

- `public System.Boolean brushing { get }`  

```csharp
public System.Boolean brushing { get; }
```

- `protected Game.Input.IProxyAction applyAction { protected get }`  

```csharp
protected Game.Input.IProxyAction applyAction { protected get; }
```

- `protected Game.Input.IProxyAction secondaryApplyAction { protected get }`  

```csharp
protected Game.Input.IProxyAction secondaryApplyAction { protected get; }
```

- `protected Game.Input.IProxyAction cancelAction { protected get }`  

```csharp
protected Game.Input.IProxyAction cancelAction { protected get; }
```

- `protected Game.Input.IProxyAction applyActionOverride { protected get; protected set }`  

```csharp
protected Game.Input.IProxyAction applyActionOverride { protected get; protected set; }
```

- `protected Game.Input.IProxyAction secondaryApplyActionOverride { protected get; protected set }`  

```csharp
protected Game.Input.IProxyAction secondaryApplyActionOverride { protected get; protected set; }
```

- `protected Game.Input.IProxyAction cancelActionOverride { protected get; protected set }`  

```csharp
protected Game.Input.IProxyAction cancelActionOverride { protected get; protected set; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> baseToolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> baseToolActions { private get; }
```

- `internal System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> actions { internal get }`  

```csharp
internal System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> actions { internal get; }
```

- `private System.Boolean actionsEnabled { private get; private set }`  

```csharp
private System.Boolean actionsEnabled { private get; private set; }
```


## Constructors

- `protected ToolBaseSystem()`  

```csharp
[Preserve]
	protected ToolBaseSystem()
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

- `protected DestroyDefinitions(Unity.Entities.EntityQuery group, Game.Tools.ToolOutputBarrier barrier, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected JobHandle DestroyDefinitions(EntityQuery group, ToolOutputBarrier barrier, JobHandle inputDeps)
	{
		if (group.IsEmptyIgnoreFilter)
		{
			return inputDeps;
		}
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new DestroyDefinitionsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CommandBuffer = barrier.CreateCommandBuffer().AsParallelWriter()
		}, group, inputDeps);
		barrier.AddJobHandleForProducer(jobHandle);
		return jobHandle;
	}
```

- `public virtual ElevationDown() : System.Void`  

```csharp
public virtual void ElevationDown()
	{
	}
```

- `public virtual ElevationScroll() : System.Void`  

```csharp
public virtual void ElevationScroll()
	{
	}
```

- `public virtual ElevationUp() : System.Void`  

```csharp
public virtual void ElevationUp()
	{
	}
```

- `protected EnsureCachedBrushData() : System.Void`  

```csharp
protected void EnsureCachedBrushData()
	{
		if (!(brushType != null))
		{
			return;
		}
		Entity entity = m_PrefabSystem.GetEntity(brushType);
		BrushData componentData = base.EntityManager.GetComponentData<BrushData>(entity);
		if (math.all(componentData.m_Resolution != 0) || brushType.m_Texture == null || brushType.m_Texture.width == 0 || brushType.m_Texture.height == 0)
		{
			return;
		}
		int2 @int = (componentData.m_Resolution = new int2(brushType.m_Texture.width, brushType.m_Texture.height));
		int num = 1;
		float num2 = 1f;
		while (math.any(componentData.m_Resolution > 128) && math.all(componentData.m_Resolution > 1))
		{
			componentData.m_Resolution /= 2;
			num *= 2;
			num2 *= 0.25f;
		}
		base.EntityManager.SetComponentData(entity, componentData);
		DynamicBuffer<BrushCell> buffer = base.EntityManager.GetBuffer<BrushCell>(entity);
		UnityEngine.Color[] pixels = brushType.m_Texture.GetPixels();
		buffer.ResizeUninitialized(componentData.m_Resolution.x * componentData.m_Resolution.y);
		int num3 = 0;
		int num4 = 0;
		for (int i = 0; i < componentData.m_Resolution.y; i++)
		{
			for (int j = 0; j < componentData.m_Resolution.x; j++)
			{
				BrushCell value = default(BrushCell);
				int num5 = num3;
				for (int k = 0; k < num; k++)
				{
					for (int l = 0; l < num; l++)
					{
						value.m_Opacity += pixels[num5++].a;
					}
					num5 += @int.x - num;
				}
				value.m_Opacity *= num2;
				buffer[num4++] = value;
				num3 += num;
			}
			num3 += @int.x * (num - 1);
		}
	}
```

- `public Equals(Game.Tools.ToolBaseSystem other) : System.Boolean`  

```csharp
public bool Equals(ToolBaseSystem other)
	{
		return this == other;
	}
```

- `protected FindDefaultBrush(Unity.Entities.EntityQuery query) : Game.Prefabs.BrushPrefab`  

```csharp
protected BrushPrefab FindDefaultBrush(EntityQuery query)
	{
		BrushPrefab result = null;
		int num = int.MaxValue;
		ComponentTypeHandle<PrefabData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<BrushData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BrushData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		NativeArray<ArchetypeChunk> nativeArray = query.ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				NativeArray<PrefabData> nativeArray2 = archetypeChunk.GetNativeArray(ref typeHandle);
				NativeArray<BrushData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle2);
				for (int j = 0; j < nativeArray3.Length; j++)
				{
					BrushData brushData = nativeArray3[j];
					if (brushData.m_Priority < num)
					{
						result = m_PrefabSystem.GetPrefab<BrushPrefab>(nativeArray2[j]);
						num = brushData.m_Priority;
					}
				}
			}
			return result;
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```

- `public static GetActualSnap(Game.Tools.Snap selectedSnap, Game.Tools.Snap onMask, Game.Tools.Snap offMask) : Game.Tools.Snap`  

```csharp
protected Snap GetActualSnap()
	{
		return GetActualSnap(selectedSnap, m_SnapOnMask, m_SnapOffMask);
	}
```

- `protected GetActualSnap() : Game.Tools.Snap`  

```csharp
protected Snap GetActualSnap()
	{
		return GetActualSnap(selectedSnap, m_SnapOnMask, m_SnapOffMask);
	}
```

- `protected virtual GetAllowApply() : System.Boolean`  

```csharp
protected virtual bool GetAllowApply()
	{
		if (m_ToolSystem.ignoreErrors || m_ErrorQuery.IsEmptyIgnoreFilter)
		{
			return !m_OriginalDeletedSystem.GetOriginalDeletedResult(0);
		}
		return false;
	}
```

- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
public virtual void GetAvailableSnapMask(out Snap onMask, out Snap offMask)
	{
		onMask = Snap.None;
		offMask = Snap.None;
	}
```

- `protected GetBrushQuery() : Unity.Entities.EntityQuery`  

```csharp
protected EntityQuery GetBrushQuery()
	{
		return GetEntityQuery(ComponentType.ReadOnly<BrushData>());
	}
```

- `protected GetContainerQuery() : Unity.Entities.EntityQuery`  

```csharp
protected EntityQuery GetContainerQuery()
	{
		return GetEntityQuery(ComponentType.ReadOnly<EditorContainerData>());
	}
```

- `protected GetContainers(Unity.Entities.EntityQuery group, Unity.Entities.Entity& laneContainer, Unity.Entities.Entity& transformContainer) : System.Boolean`  

```csharp
protected bool GetContainers(EntityQuery group, out Entity laneContainer, out Entity transformContainer)
	{
		laneContainer = Entity.Null;
		transformContainer = Entity.Null;
		if (group.IsEmptyIgnoreFilter)
		{
			return false;
		}
		NativeArray<Entity> nativeArray = group.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity entity = nativeArray[i];
			if (base.EntityManager.HasComponent<NetData>(entity))
			{
				laneContainer = entity;
			}
			else if (base.EntityManager.HasComponent<ObjectData>(entity))
			{
				transformContainer = entity;
			}
		}
		nativeArray.Dispose();
		return true;
	}
```

- `protected GetDefinitionQuery() : Unity.Entities.EntityQuery`  

```csharp
protected EntityQuery GetDefinitionQuery()
	{
		return GetEntityQuery(ComponentType.ReadOnly<CreationDefinition>(), ComponentType.Exclude<Updated>());
	}
```

- `public abstract GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public abstract Game.Prefabs.PrefabBase GetPrefab();
```

- `protected GetRaycastResult(Unity.Entities.Entity& entity, Game.Common.RaycastHit& hit) : System.Boolean`  

```csharp
protected virtual bool GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate)
	{
		if (GetRaycastResult(out var entity, out var hit, out forceUpdate))
		{
			controlPoint = new ControlPoint(entity, hit);
			return true;
		}
		controlPoint = default(ControlPoint);
		return false;
	}
```

- `protected GetRaycastResult(Unity.Entities.Entity& entity, Game.Common.RaycastHit& hit, System.Boolean& forceUpdate) : System.Boolean`  

```csharp
protected virtual bool GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate)
	{
		if (GetRaycastResult(out var entity, out var hit, out forceUpdate))
		{
			controlPoint = new ControlPoint(entity, hit);
			return true;
		}
		controlPoint = default(ControlPoint);
		return false;
	}
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint) : System.Boolean`  

```csharp
protected virtual bool GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate)
	{
		if (GetRaycastResult(out var entity, out var hit, out forceUpdate))
		{
			controlPoint = new ControlPoint(entity, hit);
			return true;
		}
		controlPoint = default(ControlPoint);
		return false;
	}
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate) : System.Boolean`  

```csharp
protected virtual bool GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate)
	{
		if (GetRaycastResult(out var entity, out var hit, out forceUpdate))
		{
			controlPoint = new ControlPoint(entity, hit);
			return true;
		}
		controlPoint = default(ControlPoint);
		return false;
	}
```

- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  

```csharp
public virtual void GetUIModes(List<ToolMode> modes)
	{
	}
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public virtual void InitializeRaycast()
	{
		m_ToolRaycastSystem.raycastFlags &= ~(RaycastFlags.ElevateOffset | RaycastFlags.SubElements | RaycastFlags.Placeholders | RaycastFlags.Markers | RaycastFlags.NoMainElements | RaycastFlags.UpgradeIsMain | RaycastFlags.OutsideConnections | RaycastFlags.Outside | RaycastFlags.Cargo | RaycastFlags.Passenger | RaycastFlags.Decals | RaycastFlags.EditorContainers | RaycastFlags.SubBuildings | RaycastFlags.PartialSurface | RaycastFlags.BuildingLots | RaycastFlags.IgnoreSecondary);
		m_ToolRaycastSystem.collisionMask = CollisionMask.OnGround | CollisionMask.Overground;
		m_ToolRaycastSystem.typeMask = TypeMask.None;
		m_ToolRaycastSystem.netLayerMask = Layer.None;
		m_ToolRaycastSystem.areaTypeMask = AreaTypeMask.None;
		m_ToolRaycastSystem.routeType = RouteType.None;
		m_ToolRaycastSystem.transportType = TransportType.None;
		m_ToolRaycastSystem.iconLayerMask = IconLayerMask.None;
		m_ToolRaycastSystem.utilityTypeMask = UtilityTypes.None;
		m_ToolRaycastSystem.rayOffset = default(float3);
	}
```

- `protected InvertBrushes(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected JobHandle InvertBrushes(EntityQuery group, JobHandle inputDeps)
	{
		if (group.IsEmptyIgnoreFilter)
		{
			return inputDeps;
		}
		return JobChunkExtensions.ScheduleParallel(new InvertBrushesJob
		{
			m_BrushType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Brush_RW_ComponentTypeHandle, ref base.CheckedStateRef)
		}, group, inputDeps);
	}
```

- `private OnActionInteraction(Game.Input.ProxyAction action, UnityEngine.InputSystem.InputActionPhase phase) : System.Void`  

```csharp
private void OnActionInteraction(ProxyAction action, InputActionPhase phase)
	{
		if (phase == InputActionPhase.Performed)
		{
			ToolBaseSystem.EventToolActionPerformed?.Invoke(action);
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_DefaultToolSystem = base.World.GetOrCreateSystemManaged<DefaultToolSystem>();
		m_ToolRaycastSystem = base.World.GetOrCreateSystemManaged<ToolRaycastSystem>();
		m_OriginalDeletedSystem = base.World.GetOrCreateSystemManaged<OriginalDeletedSystem>();
		string name = GetType().Name;
		m_DefaultApply = Game.Input.InputManager.instance.toolActionCollection.GetActionState("Apply", name);
		m_DefaultSecondaryApply = Game.Input.InputManager.instance.toolActionCollection.GetActionState("Secondary Apply", name);
		m_DefaultCancel = Game.Input.InputManager.instance.toolActionCollection.GetActionState("Cancel", name);
		m_MouseApply = Game.Input.InputManager.instance.toolActionCollection.GetActionState("Mouse Apply", name);
		m_MouseCancel = Game.Input.InputManager.instance.toolActionCollection.GetActionState("Mouse Cancel", name);
		requireAreas = AreaTypeMask.None;
		requireRoutes = RouteType.None;
		requireStops = TransportType.None;
		selectedSnap = Snap.All;
		base.Enabled = false;
		m_HasFocus = true;
		m_ErrorQuery = GetEntityQuery(ComponentType.ReadOnly<Error>());
		infomodes = new List<InfomodePrefab>();
		m_ToolSystem.tools.Add(this);
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

- `protected virtual OnFocusChanged(System.Boolean hasfocus) : System.Void`  

```csharp
protected override void OnFocusChanged(bool hasfocus)
	{
		m_FocusChanged = hasfocus != m_HasFocus;
		m_HasFocus = hasfocus;
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		base.OnStartRunning();
		m_ForceUpdate = true;
		SetActions();
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		infoview = null;
		infomodes.Clear();
		ResetActions();
		base.OnStopRunning();
	}
```

- `protected OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected virtual JobHandle OnUpdate(JobHandle inputDeps)
	{
		return inputDeps;
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected virtual JobHandle OnUpdate(JobHandle inputDeps)
	{
		return inputDeps;
	}
```

- `private virtual ResetActions() : System.Void`  

```csharp
private protected virtual void ResetActions()
	{
		SetInteraction(set: false);
		using (ProxyAction.DeferStateUpdating())
		{
			applyAction.enabled = false;
			secondaryApplyAction.enabled = false;
			cancelAction.enabled = false;
			applyActionOverride = null;
			secondaryApplyActionOverride = null;
			cancelActionOverride = null;
			actionsEnabled = true;
		}
	}
```

- `protected SetAction(Game.Input.IProxyAction& action, Game.Input.IProxyAction newAction) : System.Void`  

```csharp
protected void SetAction(ref IProxyAction action, IProxyAction newAction)
	{
		if (newAction != action)
		{
			if (action == null)
			{
				action = newAction;
			}
			else if (newAction == null)
			{
				action.enabled = false;
				action = null;
			}
			else
			{
				newAction.enabled = action.enabled;
				action.enabled = false;
				action = newAction;
			}
		}
	}
```

- `private virtual SetActions() : System.Void`  

```csharp
private protected virtual void SetActions()
	{
		UpdateActions();
		SetInteraction(set: true);
	}
```

- `private SetInteraction(System.Boolean set) : System.Void`  

```csharp
private void SetInteraction(bool set)
	{
		HashSet<ProxyAction> hashSet = new HashSet<ProxyAction>();
		foreach (IProxyAction action in actions)
		{
			if (!(action is UIBaseInputAction.IState state))
			{
				if (action is ProxyAction item)
				{
					hashSet.Add(item);
				}
				continue;
			}
			foreach (ProxyAction action2 in state.actions)
			{
				hashSet.Add(action2);
			}
		}
		foreach (ProxyAction item2 in hashSet)
		{
			if (set)
			{
				item2.onInteraction += OnActionInteraction;
			}
			else
			{
				item2.onInteraction -= OnActionInteraction;
			}
		}
	}
```

- `public virtual SetUnderground(System.Boolean underground) : System.Void`  

```csharp
public virtual void SetUnderground(bool underground)
	{
	}
```

- `public ToggleToolOptions(System.Boolean enabled) : System.Void`  

```csharp
public void ToggleToolOptions(bool enabled)
	{
		actionsEnabled = !enabled;
		UpdateActions();
	}
```

- `public abstract TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public abstract System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
```

- `private virtual UpdateActions() : System.Void`  

```csharp
private protected virtual void UpdateActions()
	{
	}
```

- `protected UpdateInfoview(Unity.Entities.Entity prefab) : System.Void`  

```csharp
protected void UpdateInfoview(Entity prefab)
	{
		infomodes.Clear();
		if (base.EntityManager.HasComponent<NetData>(prefab) && base.EntityManager.TryGetBuffer(prefab, isReadOnly: true, out DynamicBuffer<SubObject> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				SubObject subObject = buffer[i];
				if ((subObject.m_Flags & SubObjectFlags.MakeOwner) != 0)
				{
					prefab = subObject.m_Prefab;
					break;
				}
			}
		}
		if (base.EntityManager.TryGetBuffer(prefab, isReadOnly: true, out DynamicBuffer<PlaceableInfoviewItem> buffer2) && buffer2.Length != 0)
		{
			infoview = m_PrefabSystem.GetPrefab<InfoviewPrefab>(buffer2[0].m_Item);
			for (int j = 1; j < buffer2.Length; j++)
			{
				infomodes.Add(m_PrefabSystem.GetPrefab<InfomodePrefab>(buffer2[j].m_Item));
			}
		}
		else
		{
			infoview = null;
		}
	}
```


## Events

- `EventToolActionPerformed` : `System.Action<Game.Input.ProxyAction>`  

```csharp
public event System.Action<Game.Input.ProxyAction> EventToolActionPerformed;
```


## Nested types

- `Game.Tools.ToolBaseSystem+DestroyDefinitionsJob`  
- `Game.Tools.ToolBaseSystem+InvertBrushesJob`  
- `Game.Tools.ToolBaseSystem+TypeHandle`  
- `Game.Tools.ToolBaseSystem+<get_baseToolActions>d__124`  
- `Game.Tools.ToolBaseSystem+<get_toolActions>d__122`  

