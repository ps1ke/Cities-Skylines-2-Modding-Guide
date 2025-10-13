# Game.Tools.ToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ToolSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    public System.Action<Game.Tools.ToolBaseSystem> EventToolChanged;
    public System.Action<Game.Prefabs.PrefabBase> EventPrefabChanged;
    public System.Action<Game.Prefabs.InfoviewPrefab> EventInfoviewChanged;
    public System.Action EventInfomodesChanged;
    private Game.Tools.ToolBaseSystem m_ActiveTool;
    private Unity.Entities.Entity m_Selected;
    private System.Int32 <selectedIndex>k__BackingField;
    private Game.GameMode <actionMode>k__BackingField;
    private System.Boolean <ignoreErrors>k__BackingField;
    private System.Boolean <fullUpdateRequired>k__BackingField;
    private Game.Tools.ToolBaseSystem m_LastTool;
    private Game.Prefabs.InfoviewPrefab m_CurrentInfoview;
    private Game.Prefabs.InfoviewPrefab m_LastToolInfoview;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UpdateSystem m_UpdateSystem;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    private System.Collections.Generic.List<Game.Tools.ToolBaseSystem> m_Tools;
    private System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> m_LastToolInfomodes;
    private System.Collections.Generic.Dictionary<Game.Prefabs.InfoviewPrefab, System.Collections.Generic.List<Game.Prefabs.InfomodeInfo>> m_InfomodeMap;
    private UnityEngine.Vector4[] m_InfomodeColors;
    private UnityEngine.Vector4[] m_InfomodeParams;
    private System.Int32[] m_InfomodeCounts;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_Infomodes;
    private System.Single m_InfoviewTimer;
    private System.Boolean m_FullUpdateRequired;
    private System.Boolean m_InfoviewUpdateRequired;
    private System.Boolean m_IsUpdating;
    private Game.Input.InputBarrier m_ToolActionBarrier;
    private System.Collections.Generic.Dictionary<Game.Input.ProxyAction, Game.Input.InputBarrier> m_MouseToolBarriers;
    protected static const System.String kToolKeyGroup;
    protected static const System.String kToolCancelKeyGroup;
    protected static const System.String kToolApplyKeyAction;
    protected static const System.String kToolCancelKeyAction;

    public Game.Tools.ToolBaseSystem activeTool { get; set; }
    public Unity.Entities.Entity selected { get; set; }
    public System.Int32 selectedIndex { get; set; }
    public Game.Prefabs.PrefabBase activePrefab { get; }
    public Game.Prefabs.InfoviewPrefab infoview { get; set; }
    public Game.Prefabs.InfoviewPrefab activeInfoview { get; }
    public Game.GameMode actionMode { get; private set; }
    public Game.Tools.ApplyMode applyMode { get; }
    public System.Boolean ignoreErrors { get; set; }
    public System.Boolean fullUpdateRequired { get; private set; }
    public System.Collections.Generic.List<Game.Tools.ToolBaseSystem> tools { get; }

    public ToolSystem();

    private System.Void <OnCreate>b__64_3(Game.Input.InputManager+ControlScheme activeControlScheme);
    private System.Void <OnCreate>b__64_4(System.Boolean mouseOverUI);
    private System.Void Activate(Unity.Entities.Entity entity, Game.Prefabs.InfomodePrefab prefab, System.Int32 priority);
    public System.Boolean ActivatePrefabTool(Game.Prefabs.PrefabBase prefab);
    private System.Void ClearInfomodes();
    private System.Void Deactivate(Unity.Entities.Entity entity, Game.Prefabs.InfomodePrefab prefab, Game.Prefabs.InfomodeActive infomodeActive);
    private System.Void Deactivate(System.Int32 colorGroup, System.Int32 activeIndex);
    public System.Collections.Generic.List<Game.Prefabs.InfomodeInfo> GetInfomodes(Game.Prefabs.InfoviewPrefab infoview);
    public System.Collections.Generic.List<Game.Prefabs.InfomodeInfo> GetInfoviewInfomodes();
    public System.Boolean IsInfomodeActive(Game.Prefabs.InfomodePrefab prefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void RefreshInputBarrier(Game.Input.InputManager+ControlScheme activeControlScheme, System.Boolean mouseOverUI);
    public System.Void RequireFullUpdate();
    public System.Void SetInfomodeActive(Game.Prefabs.InfomodePrefab prefab, System.Boolean active, System.Int32 priority);
    public System.Void SetInfomodeActive(Unity.Entities.Entity entity, System.Boolean active, System.Int32 priority);
    private System.Void SetInfoview(Game.Prefabs.InfoviewPrefab value, System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> infomodes);
    private System.Boolean ShouldBlockBarrier(Game.Input.InputManager+ControlScheme activeControlScheme, System.Boolean mouseOverUI);
    private System.Void ToolUpdate();
    private System.Void UpdateInfoviewColors();
}
```


## Fields

- `public System.Action<Game.Tools.ToolBaseSystem> EventToolChanged`  

```csharp
public System.Action<Game.Tools.ToolBaseSystem> EventToolChanged;
```

- `public System.Action<Game.Prefabs.PrefabBase> EventPrefabChanged`  

```csharp
public System.Action<Game.Prefabs.PrefabBase> EventPrefabChanged;
```

- `public System.Action<Game.Prefabs.InfoviewPrefab> EventInfoviewChanged`  

```csharp
public System.Action<Game.Prefabs.InfoviewPrefab> EventInfoviewChanged;
```

- `public System.Action EventInfomodesChanged`  

```csharp
public System.Action EventInfomodesChanged;
```

- `private Game.Tools.ToolBaseSystem m_ActiveTool`  

```csharp
private Game.Tools.ToolBaseSystem m_ActiveTool;
```

- `private Unity.Entities.Entity m_Selected`  

```csharp
private Unity.Entities.Entity m_Selected;
```

- `private System.Int32 <selectedIndex>k__BackingField`  

```csharp
private System.Int32 <selectedIndex>k__BackingField;
```

- `private Game.GameMode <actionMode>k__BackingField`  

```csharp
private Game.GameMode <actionMode>k__BackingField;
```

- `private System.Boolean <ignoreErrors>k__BackingField`  

```csharp
private System.Boolean <ignoreErrors>k__BackingField;
```

- `private System.Boolean <fullUpdateRequired>k__BackingField`  

```csharp
private System.Boolean <fullUpdateRequired>k__BackingField;
```

- `private Game.Tools.ToolBaseSystem m_LastTool`  

```csharp
private Game.Tools.ToolBaseSystem m_LastTool;
```

- `private Game.Prefabs.InfoviewPrefab m_CurrentInfoview`  

```csharp
private Game.Prefabs.InfoviewPrefab m_CurrentInfoview;
```

- `private Game.Prefabs.InfoviewPrefab m_LastToolInfoview`  

```csharp
private Game.Prefabs.InfoviewPrefab m_LastToolInfoview;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `private System.Collections.Generic.List<Game.Tools.ToolBaseSystem> m_Tools`  

```csharp
private System.Collections.Generic.List<Game.Tools.ToolBaseSystem> m_Tools;
```

- `private System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> m_LastToolInfomodes`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> m_LastToolInfomodes;
```

- `private System.Collections.Generic.Dictionary<Game.Prefabs.InfoviewPrefab, System.Collections.Generic.List<Game.Prefabs.InfomodeInfo>> m_InfomodeMap`  

```csharp
private System.Collections.Generic.Dictionary<Game.Prefabs.InfoviewPrefab, System.Collections.Generic.List<Game.Prefabs.InfomodeInfo>> m_InfomodeMap;
```

- `private UnityEngine.Vector4[] m_InfomodeColors`  

```csharp
private UnityEngine.Vector4[] m_InfomodeColors;
```

- `private UnityEngine.Vector4[] m_InfomodeParams`  

```csharp
private UnityEngine.Vector4[] m_InfomodeParams;
```

- `private System.Int32[] m_InfomodeCounts`  

```csharp
private System.Int32[] m_InfomodeCounts;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_Infomodes`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_Infomodes;
```

- `private System.Single m_InfoviewTimer`  

```csharp
private System.Single m_InfoviewTimer;
```

- `private System.Boolean m_FullUpdateRequired`  

```csharp
private System.Boolean m_FullUpdateRequired;
```

- `private System.Boolean m_InfoviewUpdateRequired`  

```csharp
private System.Boolean m_InfoviewUpdateRequired;
```

- `private System.Boolean m_IsUpdating`  

```csharp
private System.Boolean m_IsUpdating;
```

- `private Game.Input.InputBarrier m_ToolActionBarrier`  

```csharp
private Game.Input.InputBarrier m_ToolActionBarrier;
```

- `private System.Collections.Generic.Dictionary<Game.Input.ProxyAction, Game.Input.InputBarrier> m_MouseToolBarriers`  

```csharp
private System.Collections.Generic.Dictionary<Game.Input.ProxyAction, Game.Input.InputBarrier> m_MouseToolBarriers;
```

- `protected static const System.String kToolKeyGroup`  

```csharp
protected static const System.String kToolKeyGroup;
```

- `protected static const System.String kToolCancelKeyGroup`  

```csharp
protected static const System.String kToolCancelKeyGroup;
```

- `protected static const System.String kToolApplyKeyAction`  

```csharp
protected static const System.String kToolApplyKeyAction;
```

- `protected static const System.String kToolCancelKeyAction`  

```csharp
protected static const System.String kToolCancelKeyAction;
```


## Properties

- `public Game.Tools.ToolBaseSystem activeTool { get; set }`  

```csharp
public Game.Tools.ToolBaseSystem activeTool { get; set; }
```

- `public Unity.Entities.Entity selected { get; set }`  

```csharp
public Unity.Entities.Entity selected { get; set; }
```

- `public System.Int32 selectedIndex { get; set }`  

```csharp
public System.Int32 selectedIndex { get; set; }
```

- `public Game.Prefabs.PrefabBase activePrefab { get }`  

```csharp
public Game.Prefabs.PrefabBase activePrefab { get; }
```

- `public Game.Prefabs.InfoviewPrefab infoview { get; set }`  

```csharp
public Game.Prefabs.InfoviewPrefab infoview { get; set; }
```

- `public Game.Prefabs.InfoviewPrefab activeInfoview { get }`  

```csharp
public Game.Prefabs.InfoviewPrefab activeInfoview { get; }
```

- `public Game.GameMode actionMode { get; private set }`  

```csharp
public Game.GameMode actionMode { get; private set; }
```

- `public Game.Tools.ApplyMode applyMode { get }`  

```csharp
public Game.Tools.ApplyMode applyMode { get; }
```

- `public System.Boolean ignoreErrors { get; set }`  

```csharp
public System.Boolean ignoreErrors { get; set; }
```

- `public System.Boolean fullUpdateRequired { get; private set }`  

```csharp
public System.Boolean fullUpdateRequired { get; private set; }
```

- `public System.Collections.Generic.List<Game.Tools.ToolBaseSystem> tools { get }`  

```csharp
public System.Collections.Generic.List<Game.Tools.ToolBaseSystem> tools { get; }
```


## Constructors

- `public ToolSystem()`  

```csharp
[Preserve]
	public ToolSystem()
	{
	}
```


## Methods

- `private <OnCreate>b__64_3(Game.Input.InputManager+ControlScheme activeControlScheme) : System.Void`  

```csharp
private System.Void <OnCreate>b__64_3(Game.Input.InputManager+ControlScheme activeControlScheme);
```

- `private <OnCreate>b__64_4(System.Boolean mouseOverUI) : System.Void`  

```csharp
private System.Void <OnCreate>b__64_4(System.Boolean mouseOverUI);
```

- `private Activate(Unity.Entities.Entity entity, Game.Prefabs.InfomodePrefab prefab, System.Int32 priority) : System.Void`  

```csharp
private void Activate(Entity entity, InfomodePrefab prefab, int priority)
	{
		int secondaryGroup;
		int colorGroup = prefab.GetColorGroup(out secondaryGroup);
		int index = colorGroup * 4 + ++m_InfomodeCounts[colorGroup];
		int secondaryIndex = -1;
		if (secondaryGroup != -1)
		{
			secondaryIndex = secondaryGroup * 4 + ++m_InfomodeCounts[secondaryGroup];
		}
		base.EntityManager.AddComponentData(entity, new InfomodeActive(priority, index, secondaryIndex));
	}
```

- `public ActivatePrefabTool(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public bool ActivatePrefabTool([CanBeNull] PrefabBase prefab)
	{
		if (prefab != null)
		{
			foreach (ToolBaseSystem tool in tools)
			{
				if (tool.TrySetPrefab(prefab))
				{
					activeTool = tool;
					return true;
				}
			}
		}
		activeTool = m_DefaultToolSystem;
		return false;
	}
```

- `private ClearInfomodes() : System.Void`  

```csharp
private void ClearInfomodes()
	{
		for (int i = 0; i < m_InfomodeCounts.Length; i++)
		{
			m_InfomodeCounts[i] = 0;
		}
		base.EntityManager.RemoveComponent<InfomodeActive>(m_Infomodes.AsArray());
		m_Infomodes.Clear();
	}
```

- `private Deactivate(Unity.Entities.Entity entity, Game.Prefabs.InfomodePrefab prefab, Game.Prefabs.InfomodeActive infomodeActive) : System.Void`  

```csharp
private void Deactivate(int colorGroup, int activeIndex)
	{
		int num = colorGroup * 4 + m_InfomodeCounts[colorGroup]--;
		if (activeIndex >= num)
		{
			return;
		}
		for (int i = 0; i < m_Infomodes.Length; i++)
		{
			Entity entity = m_Infomodes[i];
			InfomodeActive componentData = base.EntityManager.GetComponentData<InfomodeActive>(entity);
			if (componentData.m_Index == num)
			{
				componentData.m_Index = activeIndex;
				base.EntityManager.SetComponentData(entity, componentData);
				break;
			}
			if (componentData.m_SecondaryIndex == num)
			{
				componentData.m_SecondaryIndex = activeIndex;
				base.EntityManager.SetComponentData(entity, componentData);
				break;
			}
		}
	}
```

- `private Deactivate(System.Int32 colorGroup, System.Int32 activeIndex) : System.Void`  

```csharp
private void Deactivate(int colorGroup, int activeIndex)
	{
		int num = colorGroup * 4 + m_InfomodeCounts[colorGroup]--;
		if (activeIndex >= num)
		{
			return;
		}
		for (int i = 0; i < m_Infomodes.Length; i++)
		{
			Entity entity = m_Infomodes[i];
			InfomodeActive componentData = base.EntityManager.GetComponentData<InfomodeActive>(entity);
			if (componentData.m_Index == num)
			{
				componentData.m_Index = activeIndex;
				base.EntityManager.SetComponentData(entity, componentData);
				break;
			}
			if (componentData.m_SecondaryIndex == num)
			{
				componentData.m_SecondaryIndex = activeIndex;
				base.EntityManager.SetComponentData(entity, componentData);
				break;
			}
		}
	}
```

- `public GetInfomodes(Game.Prefabs.InfoviewPrefab infoview) : System.Collections.Generic.List<Game.Prefabs.InfomodeInfo>`  

```csharp
[CanBeNull]
	public List<InfomodeInfo> GetInfomodes(InfoviewPrefab infoview)
	{
		if (infoview == null)
		{
			return null;
		}
		if (!m_InfomodeMap.TryGetValue(infoview, out var value))
		{
			value = new List<InfomodeInfo>();
			DynamicBuffer<InfoviewMode> buffer = m_PrefabSystem.GetBuffer<InfoviewMode>(infoview, isReadOnly: true);
			for (int i = 0; i < buffer.Length; i++)
			{
				InfoviewMode infoviewMode = buffer[i];
				InfomodeInfo item = new InfomodeInfo
				{
					m_Mode = m_PrefabSystem.GetPrefab<InfomodePrefab>(infoviewMode.m_Mode),
					m_Priority = infoviewMode.m_Priority,
					m_Supplemental = infoviewMode.m_Supplemental,
					m_Optional = infoviewMode.m_Optional
				};
				value.Add(item);
			}
			value.Sort();
			m_InfomodeMap.Add(infoview, value);
		}
		return value;
	}
```

- `public GetInfoviewInfomodes() : System.Collections.Generic.List<Game.Prefabs.InfomodeInfo>`  

```csharp
public List<InfomodeInfo> GetInfoviewInfomodes()
	{
		return GetInfomodes(activeInfoview);
	}
```

- `public IsInfomodeActive(Game.Prefabs.InfomodePrefab prefab) : System.Boolean`  

```csharp
public bool IsInfomodeActive(InfomodePrefab prefab)
	{
		Entity entity = m_PrefabSystem.GetEntity(prefab);
		return base.EntityManager.HasComponent<InfomodeActive>(entity);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_UpdateSystem = base.World.GetOrCreateSystemManaged<UpdateSystem>();
		m_ToolRaycastSystem = base.World.GetOrCreateSystemManaged<ToolRaycastSystem>();
		m_DefaultToolSystem = base.World.GetOrCreateSystemManaged<DefaultToolSystem>();
		activeTool = m_DefaultToolSystem;
		m_LastToolInfomodes = new List<InfomodePrefab>();
		m_InfomodeMap = new Dictionary<InfoviewPrefab, List<InfomodeInfo>>();
		m_InfomodeColors = new Vector4[303];
		m_InfomodeParams = new Vector4[101];
		m_InfomodeCounts = new int[3];
		m_Infomodes = new NativeList<Entity>(10, Allocator.Persistent);
		m_ToolActionBarrier = Game.Input.InputManager.instance.CreateMapBarrier("Tool", "ToolSystem");
		m_ToolActionBarrier.blocked = true;
		m_MouseToolBarriers = Game.Input.InputManager.instance.FindActionMap("Tool").actions.Values.Where((ProxyAction a) => a.isMouseAction).ToDictionary((ProxyAction i) => i, (ProxyAction i) => new InputBarrier("Mouse Tool", i, Game.Input.InputManager.DeviceType.Mouse));
		foreach (KeyValuePair<ProxyAction, InputBarrier> item in m_MouseToolBarriers)
		{
			var (action, _) = (KeyValuePair<ProxyAction, InputBarrier>)(ref item);
			action.onInteraction += delegate(ProxyAction _, InputActionPhase phase)
			{
				if (phase == InputActionPhase.Canceled && m_MouseToolBarriers.TryGetValue(action, out var value))
				{
					value.blocked = ShouldBlockBarrier(Game.Input.InputManager.instance.activeControlScheme, Game.Input.InputManager.instance.mouseOverUI);
				}
			};
		}
		Game.Input.InputManager.instance.EventControlSchemeChanged += delegate(Game.Input.InputManager.ControlScheme activeControlScheme)
		{
			RefreshInputBarrier(activeControlScheme, Game.Input.InputManager.instance.mouseOverUI);
		};
		Game.Input.InputManager.instance.EventMouseOverUIChanged += delegate(bool mouseOverUI)
		{
			RefreshInputBarrier(Game.Input.InputManager.instance.activeControlScheme, mouseOverUI);
		};
		Shader.SetGlobalInt("colossal_InfoviewOn", 0);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_Infomodes.Dispose();
		Shader.SetGlobalInt("colossal_InfoviewOn", 0);
		m_ToolActionBarrier.Dispose();
		foreach (KeyValuePair<ProxyAction, InputBarrier> item in m_MouseToolBarriers)
		{
			item.Deconstruct(out var _, out var value);
			value.Dispose();
		}
		m_MouseToolBarriers = null;
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		ClearInfomodes();
		m_CurrentInfoview = null;
		Shader.SetGlobalInt("colossal_InfoviewOn", 0);
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		actionMode = mode;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_ToolActionBarrier.blocked = !GameManager.instance.gameMode.IsGameOrEditor() || GameManager.instance.isGameLoading;
		m_IsUpdating = true;
		m_UpdateSystem.Update(SystemUpdatePhase.PreTool);
		ToolUpdate();
		m_UpdateSystem.Update(SystemUpdatePhase.PostTool);
		fullUpdateRequired = m_FullUpdateRequired;
		m_FullUpdateRequired = false;
		m_IsUpdating = false;
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		ClearInfomodes();
		activeTool = m_DefaultToolSystem;
	}
```

- `private RefreshInputBarrier(Game.Input.InputManager+ControlScheme activeControlScheme, System.Boolean mouseOverUI) : System.Void`  

```csharp
private void RefreshInputBarrier(Game.Input.InputManager.ControlScheme activeControlScheme, bool mouseOverUI)
	{
		bool flag = ShouldBlockBarrier(activeControlScheme, mouseOverUI);
		foreach (KeyValuePair<ProxyAction, InputBarrier> item in m_MouseToolBarriers)
		{
			item.Deconstruct(out var key, out var value);
			ProxyAction proxyAction = key;
			value.blocked = flag && !proxyAction.IsInProgress();
		}
	}
```

- `public RequireFullUpdate() : System.Void`  

```csharp
public void RequireFullUpdate()
	{
		if (m_IsUpdating)
		{
			m_FullUpdateRequired = true;
		}
		else
		{
			fullUpdateRequired = true;
		}
	}
```

- `public SetInfomodeActive(Game.Prefabs.InfomodePrefab prefab, System.Boolean active, System.Int32 priority) : System.Void`  

```csharp
public void SetInfomodeActive(Entity entity, bool active, int priority)
	{
		if (!base.EntityManager.Exists(entity))
		{
			return;
		}
		if (!active)
		{
			int num = m_Infomodes.IndexOf(entity);
			if (num >= 0)
			{
				InfomodeActive componentData = base.EntityManager.GetComponentData<InfomodeActive>(entity);
				InfomodePrefab prefab = m_PrefabSystem.GetPrefab<InfomodePrefab>(entity);
				Deactivate(entity, prefab, componentData);
				m_Infomodes.RemoveAtSwapBack(num);
				m_InfoviewUpdateRequired = true;
				EventInfomodesChanged?.Invoke();
			}
		}
		else
		{
			if (m_Infomodes.Contains(entity))
			{
				return;
			}
			InfomodePrefab prefab2 = m_PrefabSystem.GetPrefab<InfomodePrefab>(entity);
			int secondaryGroup;
			int colorGroup = prefab2.GetColorGroup(out secondaryGroup);
			bool flag = false;
			for (int i = 0; i < m_Infomodes.Length; i++)
			{
				Entity entity2 = m_Infomodes[i];
				InfomodePrefab prefab3 = m_PrefabSystem.GetPrefab<InfomodePrefab>(entity2);
				int secondaryGroup2;
				int colorGroup2 = prefab3.GetColorGroup(out secondaryGroup2);
				if ((colorGroup2 == colorGroup || colorGroup2 == secondaryGroup || secondaryGroup2 == colorGroup || (secondaryGroup2 == secondaryGroup && secondaryGroup2 != -1)) && !prefab2.CanActivateBoth(prefab3))
				{
					InfomodeActive componentData2 = base.EntityManager.GetComponentData<InfomodeActive>(entity2);
					Deactivate(entity2, prefab3, componentData2);
					m_Infomodes[i] = entity;
					flag = true;
					break;
				}
			}
			Activate(entity, prefab2, priority);
			if (!flag)
			{
				m_Infomodes.Add(in entity);
			}
			m_InfoviewUpdateRequired = true;
			EventInfomodesChanged?.Invoke();
		}
	}
```

- `public SetInfomodeActive(Unity.Entities.Entity entity, System.Boolean active, System.Int32 priority) : System.Void`  

```csharp
public void SetInfomodeActive(Entity entity, bool active, int priority)
	{
		if (!base.EntityManager.Exists(entity))
		{
			return;
		}
		if (!active)
		{
			int num = m_Infomodes.IndexOf(entity);
			if (num >= 0)
			{
				InfomodeActive componentData = base.EntityManager.GetComponentData<InfomodeActive>(entity);
				InfomodePrefab prefab = m_PrefabSystem.GetPrefab<InfomodePrefab>(entity);
				Deactivate(entity, prefab, componentData);
				m_Infomodes.RemoveAtSwapBack(num);
				m_InfoviewUpdateRequired = true;
				EventInfomodesChanged?.Invoke();
			}
		}
		else
		{
			if (m_Infomodes.Contains(entity))
			{
				return;
			}
			InfomodePrefab prefab2 = m_PrefabSystem.GetPrefab<InfomodePrefab>(entity);
			int secondaryGroup;
			int colorGroup = prefab2.GetColorGroup(out secondaryGroup);
			bool flag = false;
			for (int i = 0; i < m_Infomodes.Length; i++)
			{
				Entity entity2 = m_Infomodes[i];
				InfomodePrefab prefab3 = m_PrefabSystem.GetPrefab<InfomodePrefab>(entity2);
				int secondaryGroup2;
				int colorGroup2 = prefab3.GetColorGroup(out secondaryGroup2);
				if ((colorGroup2 == colorGroup || colorGroup2 == secondaryGroup || secondaryGroup2 == colorGroup || (secondaryGroup2 == secondaryGroup && secondaryGroup2 != -1)) && !prefab2.CanActivateBoth(prefab3))
				{
					InfomodeActive componentData2 = base.EntityManager.GetComponentData<InfomodeActive>(entity2);
					Deactivate(entity2, prefab3, componentData2);
					m_Infomodes[i] = entity;
					flag = true;
					break;
				}
			}
			Activate(entity, prefab2, priority);
			if (!flag)
			{
				m_Infomodes.Add(in entity);
			}
			m_InfoviewUpdateRequired = true;
			EventInfomodesChanged?.Invoke();
		}
	}
```

- `private SetInfoview(Game.Prefabs.InfoviewPrefab value, System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> infomodes) : System.Void`  

```csharp
private void SetInfoview(InfoviewPrefab value, List<InfomodePrefab> infomodes)
	{
		m_CurrentInfoview = value;
		ClearInfomodes();
		if (activeInfoview != null)
		{
			List<InfomodeInfo> infomodes2 = GetInfomodes(value);
			for (int i = 0; i < infomodes2.Count; i++)
			{
				InfomodeInfo infomodeInfo = infomodes2[i];
				if ((!infomodeInfo.m_Supplemental || (infomodes != null && infomodes.Contains(infomodeInfo.m_Mode))) && (!infomodeInfo.m_Optional || !actionMode.IsGame() || infomodes == null || infomodes.Contains(infomodeInfo.m_Mode)))
				{
					Entity value2 = m_PrefabSystem.GetEntity(infomodeInfo.m_Mode);
					Activate(value2, infomodeInfo.m_Mode, infomodeInfo.m_Priority);
					m_Infomodes.Add(in value2);
				}
			}
		}
		m_InfoviewTimer = 0f;
		m_InfoviewUpdateRequired = true;
		EventInfoviewChanged?.Invoke(value);
	}
```

- `private ShouldBlockBarrier(Game.Input.InputManager+ControlScheme activeControlScheme, System.Boolean mouseOverUI) : System.Boolean`  

```csharp
private bool ShouldBlockBarrier(Game.Input.InputManager.ControlScheme activeControlScheme, bool mouseOverUI)
	{
		return activeControlScheme == Game.Input.InputManager.ControlScheme.KeyboardAndMouse && mouseOverUI;
	}
```

- `private ToolUpdate() : System.Void`  

```csharp
private void ToolUpdate()
	{
		m_InfoviewTimer += UnityEngine.Time.deltaTime;
		m_InfoviewTimer %= 60f;
		if (activeTool != m_LastTool)
		{
			if (m_LastTool != null)
			{
				m_LastTool.Enabled = false;
				m_LastTool.Update();
			}
			m_LastTool = activeTool;
		}
		InfoviewPrefab infoviewPrefab = null;
		List<InfomodePrefab> list = null;
		if (m_LastTool != null)
		{
			m_LastTool.Enabled = true;
		}
		m_UpdateSystem.Update(SystemUpdatePhase.ToolUpdate);
		if (m_LastTool != null)
		{
			infoviewPrefab = m_LastTool.infoview;
			list = m_LastTool.infomodes;
		}
		if (infoviewPrefab != m_LastToolInfoview)
		{
			SetInfoview(infoviewPrefab, list);
			m_LastToolInfoview = infoviewPrefab;
			m_LastToolInfomodes.Clear();
			if (list != null)
			{
				m_LastToolInfomodes.AddRange(list);
			}
		}
		else if (infoviewPrefab != null && infoviewPrefab == activeInfoview)
		{
			if ((list != null && list.Count != 0) || m_LastToolInfomodes.Count != 0)
			{
				List<InfomodeInfo> infomodes = GetInfomodes(infoviewPrefab);
				for (int i = 0; i < infomodes.Count; i++)
				{
					InfomodeInfo infomodeInfo = infomodes[i];
					if (infomodeInfo.m_Supplemental || (infomodeInfo.m_Optional && actionMode.IsGame()))
					{
						bool num = m_LastToolInfomodes.Contains(infomodeInfo.m_Mode);
						bool flag = list?.Contains(infomodeInfo.m_Mode) ?? false;
						if (num != flag)
						{
							Entity entity = m_PrefabSystem.GetEntity(infomodeInfo.m_Mode);
							SetInfomodeActive(entity, flag, infomodeInfo.m_Priority);
						}
					}
				}
			}
			m_LastToolInfomodes.Clear();
			if (list != null)
			{
				m_LastToolInfomodes.AddRange(list);
			}
		}
		if (m_InfoviewUpdateRequired)
		{
			m_InfoviewUpdateRequired = false;
			UpdateInfoviewColors();
		}
		Shader.SetGlobalFloat("colossal_InfoviewTime", m_InfoviewTimer);
	}
```

- `private UpdateInfoviewColors() : System.Void`  

```csharp
private void UpdateInfoviewColors()
	{
		if (activeInfoview != null)
		{
			m_InfomodeColors[0] = activeInfoview.m_DefaultColor.linear;
			m_InfomodeColors[1] = activeInfoview.m_DefaultColor.linear;
			m_InfomodeColors[2] = activeInfoview.m_SecondaryColor.linear;
			m_InfomodeParams[0] = new Vector4(1f, 0f, 0f, 0f);
			for (int i = 0; i < m_Infomodes.Length; i++)
			{
				Entity entity = m_Infomodes[i];
				InfomodePrefab prefab = m_PrefabSystem.GetPrefab<InfomodePrefab>(entity);
				InfomodeActive componentData = base.EntityManager.GetComponentData<InfomodeActive>(entity);
				prefab.GetColors(out var color, out var color2, out var color3, out var steps, out var speed, out var tiling, out var fill);
				m_InfomodeColors[componentData.m_Index * 3] = color.linear;
				m_InfomodeColors[componentData.m_Index * 3 + 1] = color2.linear;
				m_InfomodeColors[componentData.m_Index * 3 + 2] = color3.linear;
				m_InfomodeParams[componentData.m_Index] = new Vector4(steps, speed, tiling, fill);
				if (componentData.m_SecondaryIndex != -1)
				{
					m_InfomodeColors[componentData.m_SecondaryIndex * 3] = color.linear;
					m_InfomodeColors[componentData.m_SecondaryIndex * 3 + 1] = color2.linear;
					m_InfomodeColors[componentData.m_SecondaryIndex * 3 + 2] = color3.linear;
					m_InfomodeParams[componentData.m_SecondaryIndex] = new Vector4(steps, speed, tiling, fill);
				}
			}
			for (int j = 0; j < m_InfomodeCounts.Length; j++)
			{
				for (int k = m_InfomodeCounts[j]; k < 4; k++)
				{
					int num = 1 + j * 4 + k;
					m_InfomodeColors[num * 3] = default(Vector4);
					m_InfomodeColors[num * 3 + 1] = default(Vector4);
					m_InfomodeColors[num * 3 + 2] = default(Vector4);
					m_InfomodeParams[num] = new Vector4(1f, 0f, 0f, 0f);
				}
			}
			Shader.SetGlobalInt("colossal_InfoviewOn", 1);
			Shader.SetGlobalVectorArray("colossal_InfomodeColors", m_InfomodeColors);
			Shader.SetGlobalVectorArray("colossal_InfomodeParams", m_InfomodeParams);
		}
		else
		{
			Shader.SetGlobalInt("colossal_InfoviewOn", 0);
		}
	}
```


## Nested types

- `Game.Tools.ToolSystem+<>c`  
- `Game.Tools.ToolSystem+<>c__DisplayClass64_0`  

