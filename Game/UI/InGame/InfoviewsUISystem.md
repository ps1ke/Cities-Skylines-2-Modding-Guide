# Game.UI.InGame.InfoviewsUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InfoviewsUISystem : Game.UI.UISystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.UnlockSystem m_UnlockSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.Prefabs.InfoviewInitializeSystem m_InfoviewInitializeSystem;
    private Colossal.UI.Binding.RawValueBinding m_ActiveView;
    private System.Collections.Generic.List<Game.UI.InGame.InfoviewsUISystem+Infoview> m_InfoviewsCache;
    private Colossal.UI.Binding.RawValueBinding m_Infoviews;
    private Unity.Entities.EntityQuery m_UnlockedInfoviewQuery;
    private System.Boolean m_InfoviewChanged;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }

    public InfoviewsUISystem();

    private System.Void BindActiveInfoview(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindColorLegend(Colossal.UI.Binding.IJsonWriter writer, UnityEngine.Color color, Game.UI.Localization.LocalizedString label);
    private System.Void BindColorLegends(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.IGradientInfomode gradientInfomode);
    private System.Void BindGradientStop(Colossal.UI.Binding.IJsonWriter writer, System.Single offset, UnityEngine.Color color);
    private System.Void BindInfomode(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.InfomodeInfo info);
    private System.Void BindInfomodeGradientLegend(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.IGradientInfomode gradientInfomode);
    private System.Void BindInfoviews(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void OnChanged();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnInfoviewChanged(Game.Prefabs.InfoviewPrefab prefab);
    protected virtual System.Void OnUpdate();
    public System.Void SetActiveInfoview(Unity.Entities.Entity entity);
    private System.Void SetInfomodeActive(Unity.Entities.Entity entity, System.Boolean active, System.Int32 priority);
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.UnlockSystem m_UnlockSystem`  

```csharp
private Game.Prefabs.UnlockSystem m_UnlockSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.Prefabs.InfoviewInitializeSystem m_InfoviewInitializeSystem`  

```csharp
private Game.Prefabs.InfoviewInitializeSystem m_InfoviewInitializeSystem;
```

- `private Colossal.UI.Binding.RawValueBinding m_ActiveView`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ActiveView;
```

- `private System.Collections.Generic.List<Game.UI.InGame.InfoviewsUISystem+Infoview> m_InfoviewsCache`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.InfoviewsUISystem+Infoview> m_InfoviewsCache;
```

- `private Colossal.UI.Binding.RawValueBinding m_Infoviews`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_Infoviews;
```

- `private Unity.Entities.EntityQuery m_UnlockedInfoviewQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedInfoviewQuery;
```

- `private System.Boolean m_InfoviewChanged`  

```csharp
private System.Boolean m_InfoviewChanged;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```


## Constructors

- `public InfoviewsUISystem()`  

```csharp
[Preserve]
	public InfoviewsUISystem()
	{
	}
```


## Methods

- `private BindActiveInfoview(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void BindActiveInfoview(IJsonWriter writer)
	{
		InfoviewPrefab activeInfoview = m_ToolSystem.activeInfoview;
		if (activeInfoview != null)
		{
			Entity entity = m_PrefabSystem.GetEntity(activeInfoview);
			writer.TypeBegin("infoviews.ActiveInfoview");
			writer.PropertyName("entity");
			writer.Write(entity);
			writer.PropertyName("id");
			writer.Write(activeInfoview.name);
			writer.PropertyName("icon");
			writer.Write(activeInfoview.m_IconPath);
			writer.PropertyName("uiTag");
			writer.Write(activeInfoview.uiTag);
			List<InfomodeInfo> infoviewInfomodes = m_ToolSystem.GetInfoviewInfomodes();
			writer.PropertyName("infomodes");
			writer.ArrayBegin(infoviewInfomodes.Count);
			for (int i = 0; i < infoviewInfomodes.Count; i++)
			{
				BindInfomode(writer, infoviewInfomodes[i]);
			}
			writer.ArrayEnd();
			writer.PropertyName("editor");
			writer.Write(activeInfoview.m_Editor);
			writer.TypeEnd();
		}
		else
		{
			writer.WriteNull();
		}
	}
```

- `private BindColorLegend(Colossal.UI.Binding.IJsonWriter writer, UnityEngine.Color color, Game.UI.Localization.LocalizedString label) : System.Void`  

```csharp
private void BindColorLegend(IJsonWriter writer, Color color, LocalizedString label)
	{
		writer.TypeBegin("infoviews.ColorLegend");
		writer.PropertyName("color");
		writer.Write(color);
		writer.PropertyName("label");
		writer.Write(label);
		writer.TypeEnd();
	}
```

- `private BindColorLegends(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.IGradientInfomode gradientInfomode) : System.Void`  

```csharp
private void BindColorLegends(IJsonWriter writer, IGradientInfomode gradientInfomode)
	{
		uint num = 0u;
		if (gradientInfomode.lowLabel.HasValue)
		{
			num++;
		}
		if (gradientInfomode.mediumLabel.HasValue)
		{
			num++;
		}
		if (gradientInfomode.highLabel.HasValue)
		{
			num++;
		}
		writer.ArrayBegin(num);
		if (gradientInfomode.lowLabel.HasValue)
		{
			BindColorLegend(writer, gradientInfomode.lowColor, gradientInfomode.lowLabel.Value);
		}
		if (gradientInfomode.mediumLabel.HasValue)
		{
			BindColorLegend(writer, gradientInfomode.mediumColor, gradientInfomode.mediumLabel.Value);
		}
		if (gradientInfomode.highLabel.HasValue)
		{
			BindColorLegend(writer, gradientInfomode.highColor, gradientInfomode.highLabel.Value);
		}
		writer.ArrayEnd();
	}
```

- `private BindGradientStop(Colossal.UI.Binding.IJsonWriter writer, System.Single offset, UnityEngine.Color color) : System.Void`  

```csharp
private void BindGradientStop(IJsonWriter writer, float offset, Color color)
	{
		writer.TypeBegin("infoviews.GradientStop");
		writer.PropertyName("offset");
		writer.Write(offset);
		writer.PropertyName("color");
		writer.Write(color);
		writer.TypeEnd();
	}
```

- `private BindInfomode(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.InfomodeInfo info) : System.Void`  

```csharp
private void BindInfomode(IJsonWriter writer, InfomodeInfo info)
	{
		Entity entity = m_PrefabSystem.GetEntity(info.m_Mode);
		IColorInfomode colorInfomode = info.m_Mode as IColorInfomode;
		IGradientInfomode gradientInfomode = info.m_Mode as IGradientInfomode;
		writer.TypeBegin("infoviews.Infomode");
		writer.PropertyName("entity");
		writer.Write(entity);
		writer.PropertyName("id");
		writer.Write(info.m_Mode.name);
		writer.PropertyName("uiTag");
		writer.Write(info.m_Mode.uiTag);
		writer.PropertyName("active");
		writer.Write(m_ToolSystem.IsInfomodeActive(info.m_Mode));
		writer.PropertyName("priority");
		writer.Write(info.m_Priority);
		writer.PropertyName("color");
		if (colorInfomode != null)
		{
			writer.Write(colorInfomode.color);
		}
		else if (gradientInfomode != null && gradientInfomode.legendType == GradientLegendType.Fields && !gradientInfomode.lowLabel.HasValue)
		{
			writer.Write(gradientInfomode.lowColor);
		}
		else
		{
			writer.WriteNull();
		}
		writer.PropertyName("gradientLegend");
		if (gradientInfomode != null && gradientInfomode.legendType == GradientLegendType.Gradient)
		{
			BindInfomodeGradientLegend(writer, gradientInfomode);
		}
		else
		{
			writer.WriteNull();
		}
		writer.PropertyName("colorLegends");
		if (gradientInfomode != null && gradientInfomode.legendType == GradientLegendType.Fields)
		{
			BindColorLegends(writer, gradientInfomode);
		}
		else
		{
			writer.WriteEmptyArray();
		}
		writer.PropertyName("type");
		writer.Write(info.m_Mode.infomodeTypeLocaleKey);
		writer.TypeEnd();
	}
```

- `private BindInfomodeGradientLegend(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.IGradientInfomode gradientInfomode) : System.Void`  

```csharp
private void BindInfomodeGradientLegend(IJsonWriter writer, IGradientInfomode gradientInfomode)
	{
		writer.TypeBegin("infoviews.InfomodeGradientLegend");
		writer.PropertyName("lowLabel");
		writer.Write(gradientInfomode.lowLabel);
		writer.PropertyName("highLabel");
		writer.Write(gradientInfomode.highLabel);
		writer.PropertyName("gradient");
		writer.TypeBegin("infoviews.Gradient");
		writer.PropertyName("stops");
		writer.ArrayBegin(3u);
		BindGradientStop(writer, 0f, gradientInfomode.lowColor);
		BindGradientStop(writer, 0.5f, gradientInfomode.mediumColor);
		BindGradientStop(writer, 1f, gradientInfomode.highColor);
		writer.ArrayEnd();
		writer.TypeEnd();
		writer.TypeEnd();
	}
```

- `private BindInfoviews(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void BindInfoviews(IJsonWriter writer)
	{
		m_InfoviewsCache.Clear();
		foreach (InfoviewPrefab infoview in m_InfoviewInitializeSystem.infoviews)
		{
			if (infoview.isValid)
			{
				bool locked = m_UnlockSystem.IsLocked(infoview);
				m_InfoviewsCache.Add(new Infoview(m_PrefabSystem.GetEntity(infoview), infoview, locked));
			}
		}
		m_InfoviewsCache.Sort();
		writer.ArrayBegin(m_InfoviewsCache.Count);
		foreach (Infoview item in m_InfoviewsCache)
		{
			item.Write(m_PrefabUISystem, writer);
		}
		writer.ArrayEnd();
	}
```

- `private OnChanged() : System.Void`  

```csharp
private void OnChanged()
	{
		m_InfoviewChanged = true;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_UnlockedInfoviewQuery = GetEntityQuery(ComponentType.ReadOnly<Unlock>());
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_UnlockSystem = base.World.GetOrCreateSystemManaged<UnlockSystem>();
		m_PrefabUISystem = base.World.GetOrCreateSystemManaged<PrefabUISystem>();
		m_InfoviewInitializeSystem = base.World.GetOrCreateSystemManaged<InfoviewInitializeSystem>();
		m_InfoviewsCache = new List<Infoview>();
		AddBinding(new TriggerBinding<Entity>("infoviews", "setActiveInfoview", SetActiveInfoview));
		AddBinding(new TriggerBinding<Entity, bool, int>("infoviews", "setInfomodeActive", SetInfomodeActive));
		AddBinding(m_Infoviews = new RawValueBinding("infoviews", "infoviews", BindInfoviews));
		AddBinding(m_ActiveView = new RawValueBinding("infoviews", "activeInfoview", BindActiveInfoview));
		ToolSystem toolSystem = m_ToolSystem;
		toolSystem.EventInfoviewChanged = (Action<InfoviewPrefab>)Delegate.Combine(toolSystem.EventInfoviewChanged, new Action<InfoviewPrefab>(OnInfoviewChanged));
		ToolSystem toolSystem2 = m_ToolSystem;
		toolSystem2.EventInfomodesChanged = (Action)Delegate.Combine(toolSystem2.EventInfomodesChanged, new Action(OnChanged));
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		ToolSystem toolSystem = m_ToolSystem;
		toolSystem.EventInfoviewChanged = (Action<InfoviewPrefab>)Delegate.Remove(toolSystem.EventInfoviewChanged, new Action<InfoviewPrefab>(OnInfoviewChanged));
		ToolSystem toolSystem2 = m_ToolSystem;
		toolSystem2.EventInfomodesChanged = (Action)Delegate.Remove(toolSystem2.EventInfomodesChanged, new Action(OnChanged));
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_Infoviews.Update();
		m_ActiveView.Update();
	}
```

- `private OnInfoviewChanged(Game.Prefabs.InfoviewPrefab prefab) : System.Void`  

```csharp
private void OnInfoviewChanged(InfoviewPrefab prefab)
	{
		m_InfoviewChanged = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (PrefabUtils.HasUnlockedPrefab<InfoviewData>(base.EntityManager, m_UnlockedInfoviewQuery))
		{
			m_Infoviews.Update();
		}
		if (m_InfoviewChanged)
		{
			m_ActiveView.Update();
			m_InfoviewChanged = false;
		}
	}
```

- `public SetActiveInfoview(Unity.Entities.Entity entity) : System.Void`  

```csharp
public void SetActiveInfoview(Entity entity)
	{
		InfoviewPrefab infoview = null;
		if (base.EntityManager.Exists(entity))
		{
			infoview = m_PrefabSystem.GetPrefab<InfoviewPrefab>(entity);
		}
		m_ToolSystem.infoview = infoview;
	}
```

- `private SetInfomodeActive(Unity.Entities.Entity entity, System.Boolean active, System.Int32 priority) : System.Void`  

```csharp
private void SetInfomodeActive(Entity entity, bool active, int priority)
	{
		m_ToolSystem.SetInfomodeActive(entity, active, priority);
	}
```


## Nested types

- `Game.UI.InGame.InfoviewsUISystem+Infoview`  

