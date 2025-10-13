# Game.Tools.UpgradeToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ObjectToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpgradeToolSystem : Game.Tools.ObjectToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Audio.AudioManager m_AudioManager;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Unity.Entities.EntityQuery m_ContainerQuery;
    private Unity.Entities.Entity m_UpgradingObject;
    private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
    private Game.Common.RandomSeed m_RandomSeed;
    private System.Boolean m_AlreadyCreated;
    private Game.Prefabs.ObjectPrefab m_Prefab;
    private Game.Input.IProxyAction m_PlaceUpgrade;
    private Game.Input.IProxyAction m_Rebuild;
    private Game.Tools.UpgradeToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public Game.Prefabs.ObjectPrefab prefab { get; set; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }

    public UpgradeToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle CreateTempObject(Unity.Jobs.JobHandle inputDeps);
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    public virtual System.Void InitializeRaycast();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

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

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Unity.Entities.EntityQuery m_ContainerQuery`  

```csharp
private Unity.Entities.EntityQuery m_ContainerQuery;
```

- `private Unity.Entities.Entity m_UpgradingObject`  

```csharp
private Unity.Entities.Entity m_UpgradingObject;
```

- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  

```csharp
private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
```

- `private Game.Common.RandomSeed m_RandomSeed`  

```csharp
private Game.Common.RandomSeed m_RandomSeed;
```

- `private System.Boolean m_AlreadyCreated`  

```csharp
private System.Boolean m_AlreadyCreated;
```

- `private Game.Prefabs.ObjectPrefab m_Prefab`  

```csharp
private Game.Prefabs.ObjectPrefab m_Prefab;
```

- `private Game.Input.IProxyAction m_PlaceUpgrade`  

```csharp
private Game.Input.IProxyAction m_PlaceUpgrade;
```

- `private Game.Input.IProxyAction m_Rebuild`  

```csharp
private Game.Input.IProxyAction m_Rebuild;
```

- `private Game.Tools.UpgradeToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.UpgradeToolSystem+TypeHandle __TypeHandle;
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

- `public Game.Prefabs.ObjectPrefab prefab { get; set }`  

```csharp
public Game.Prefabs.ObjectPrefab prefab { get; set; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```


## Constructors

- `public UpgradeToolSystem()`  

```csharp
[Preserve]
	public UpgradeToolSystem()
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

- `private Apply(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Apply(JobHandle inputDeps)
	{
		if (GetAllowApply())
		{
			m_ToolSystem.activeTool = m_DefaultToolSystem;
			base.applyMode = ApplyMode.Apply;
			m_RandomSeed = RandomSeed.Next();
			m_AlreadyCreated = false;
			m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PlaceUpgradeSound);
			if (m_ToolSystem.actionMode.IsGame() && prefab != null)
			{
				Game.Objects.Transform componentData = base.EntityManager.GetComponentData<Game.Objects.Transform>(m_UpgradingObject);
				Telemetry.PlaceBuilding(m_UpgradingObject, prefab, componentData.m_Position);
			}
			return inputDeps;
		}
		m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PlaceBuildingFailSound);
		return Update(inputDeps);
	}
```

- `private Cancel(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Cancel(JobHandle inputDeps)
	{
		m_ToolSystem.activeTool = m_DefaultToolSystem;
		base.applyMode = ApplyMode.Clear;
		m_AlreadyCreated = false;
		return inputDeps;
	}
```

- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Clear(JobHandle inputDeps)
	{
		base.applyMode = ApplyMode.Clear;
		m_AlreadyCreated = false;
		return inputDeps;
	}
```

- `private CreateTempObject(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle CreateTempObject(JobHandle inputDeps)
	{
		Game.Objects.Transform componentData = base.EntityManager.GetComponentData<Game.Objects.Transform>(m_UpgradingObject);
		ControlPoint value = new ControlPoint
		{
			m_Position = componentData.m_Position,
			m_Rotation = componentData.m_Rotation
		};
		if (prefab != null && m_PrefabSystem.HasComponent<BuildingExtensionData>(prefab))
		{
			BuildingExtensionData componentData2 = m_PrefabSystem.GetComponentData<BuildingExtensionData>(prefab);
			value.m_Position = ObjectUtils.LocalToWorld(componentData, componentData2.m_Position);
		}
		m_ControlPoints.Clear();
		m_ControlPoints.Add(in value);
		return UpdateDefinitions(inputDeps);
	}
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public override PrefabBase GetPrefab()
	{
		return prefab;
	}
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public override void InitializeRaycast()
	{
		base.InitializeRaycast();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_DefinitionQuery = GetDefinitionQuery();
		m_ContainerQuery = GetContainerQuery();
		m_SoundQuery = GetEntityQuery(ComponentType.ReadOnly<ToolUXSoundSettingsData>());
		m_PlaceUpgrade = InputManager.instance.toolActionCollection.GetActionState("Place Upgrade", "UpgradeToolSystem");
		m_Rebuild = InputManager.instance.toolActionCollection.GetActionState("Rebuild", "UpgradeToolSystem");
		m_ControlPoints = new NativeList<ControlPoint>(1, Allocator.Persistent);
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
		m_RandomSeed = RandomSeed.Next();
		m_AlreadyCreated = false;
		base.requireZones = true;
		base.requireAreas = AreaTypeMask.Lots;
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		m_UpgradingObject = m_ToolSystem.selected;
		if (prefab != null)
		{
			if (!base.EntityManager.HasBuffer<InstalledUpgrade>(m_UpgradingObject))
			{
				m_UpgradingObject = Entity.Null;
			}
			if (m_PrefabSystem.TryGetComponentData<BuildingExtensionData>(prefab, out var component) && component.m_HasUndergroundElements)
			{
				base.requireNet |= Layer.Road;
			}
			UpdateInfoview(m_PrefabSystem.GetEntity(prefab));
		}
		else
		{
			if (!base.EntityManager.HasComponent<Destroyed>(m_UpgradingObject))
			{
				m_UpgradingObject = Entity.Null;
			}
			UpdateInfoview(Entity.Null);
		}
		GetAvailableSnapMask(out m_SnapOnMask, out m_SnapOffMask);
		UpdateActions();
		if (m_UpgradingObject != Entity.Null && !m_ToolSystem.fullUpdateRequired && (m_ToolRaycastSystem.raycastFlags & (RaycastFlags.DebugDisable | RaycastFlags.UIDisable)) == 0)
		{
			if (base.cancelAction.WasPressedThisFrame())
			{
				return Cancel(inputDeps);
			}
			if (base.applyAction.WasPressedThisFrame())
			{
				return Apply(inputDeps);
			}
			return Update(inputDeps);
		}
		return Clear(inputDeps);
	}
```

- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public override bool TrySetPrefab(PrefabBase prefab)
	{
		if (!m_ToolSystem.actionMode.IsEditor() && prefab is ObjectPrefab objectPrefab && prefab.Has<Game.Prefabs.ServiceUpgrade>())
		{
			Entity entity = m_PrefabSystem.GetEntity(prefab);
			if (InternalCompilerInterface.HasComponentAfterCompletingDependency(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RO_ComponentLookup, ref base.CheckedStateRef, entity))
			{
				return false;
			}
			this.prefab = objectPrefab;
			return true;
		}
		return false;
	}
```

- `private Update(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Update(JobHandle inputDeps)
	{
		if (m_ToolSystem.selected == Entity.Null)
		{
			base.applyMode = ApplyMode.Clear;
			m_AlreadyCreated = false;
			return inputDeps;
		}
		if (m_AlreadyCreated && !m_ForceUpdate)
		{
			base.applyMode = ApplyMode.None;
			return inputDeps;
		}
		base.applyMode = ApplyMode.Clear;
		m_AlreadyCreated = true;
		return CreateTempObject(inputDeps);
	}
```

- `private virtual UpdateActions() : System.Void`  

```csharp
private protected override void UpdateActions()
	{
		using (ProxyAction.DeferStateUpdating())
		{
			base.applyActionOverride = ((prefab != null) ? m_PlaceUpgrade : m_Rebuild);
			base.applyAction.enabled = base.actionsEnabled && GetAllowApply();
			base.cancelActionOverride = m_MouseCancel;
			base.cancelAction.enabled = base.actionsEnabled;
		}
	}
```

- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateDefinitions(JobHandle inputDeps)
	{
		JobHandle jobHandle = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
		if (m_UpgradingObject != Entity.Null)
		{
			Entity objectPrefab = Entity.Null;
			if (prefab != null)
			{
				objectPrefab = m_PrefabSystem.GetEntity(prefab);
			}
			Entity laneContainer = Entity.Null;
			if (m_ToolSystem.actionMode.IsEditor())
			{
				GetContainers(m_ContainerQuery, out laneContainer, out var _);
			}
			jobHandle = JobHandle.CombineDependencies(jobHandle, CreateDefinitions(objectPrefab, Entity.Null, Entity.Null, m_UpgradingObject, Entity.Null, laneContainer, m_CityConfigurationSystem.defaultTheme, m_ControlPoints, default(NativeReference<AttachmentData>), m_ToolSystem.actionMode.IsEditor(), m_CityConfigurationSystem.leftHandTraffic, removing: false, stamping: false, base.brushSize, math.radians(base.brushAngle), base.brushStrength, 0f, UnityEngine.Time.deltaTime, m_RandomSeed, GetActualSnap(), AgeMask.Sapling, inputDeps));
		}
		return jobHandle;
	}
```


## Nested types

- `Game.Tools.UpgradeToolSystem+TypeHandle`  
- `Game.Tools.UpgradeToolSystem+<get_toolActions>d__19`  

