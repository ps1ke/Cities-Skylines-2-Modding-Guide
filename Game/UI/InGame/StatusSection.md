# Game.UI.InGame.StatusSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StatusSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> <conditions>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.Notification> <notifications>k__BackingField;
    private Game.UI.InGame.CitizenHappiness <happiness>k__BackingField;
    private Game.UI.ImageSystem m_ImageSystem;
    private System.Boolean m_Dead;

    protected System.String group { protected get; }
    private Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> conditions { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications { private get; private set; }
    private Game.UI.InGame.CitizenHappiness happiness { private get; private set; }

    public StatusSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> <conditions>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> <conditions>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.Notification> <notifications>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.Notification> <notifications>k__BackingField;
```

- `private Game.UI.InGame.CitizenHappiness <happiness>k__BackingField`  

```csharp
private Game.UI.InGame.CitizenHappiness <happiness>k__BackingField;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private System.Boolean m_Dead`  

```csharp
private System.Boolean m_Dead;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> conditions { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> conditions { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications { private get; private set; }
```

- `private Game.UI.InGame.CitizenHappiness happiness { private get; private set }`  

```csharp
private Game.UI.InGame.CitizenHappiness happiness { private get; private set; }
```


## Constructors

- `public StatusSection()`  

```csharp
[Preserve]
	public StatusSection()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		conditions = new NativeList<CitizenCondition>(Allocator.Persistent);
		notifications = new NativeList<Notification>(Allocator.Persistent);
		m_ImageSystem = base.World.GetOrCreateSystemManaged<ImageSystem>();
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		conditions.Dispose();
		notifications.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		Citizen componentData = base.EntityManager.GetComponentData<Citizen>(selectedEntity);
		HouseholdMember componentData2 = base.EntityManager.GetComponentData<HouseholdMember>(selectedEntity);
		happiness = CitizenUIUtils.GetCitizenHappiness(componentData);
		conditions = CitizenUIUtils.GetCitizenConditions(base.EntityManager, selectedEntity, componentData, componentData2, conditions);
		notifications = NotificationsSection.GetNotifications(base.EntityManager, selectedEntity, notifications);
		if (base.EntityManager.TryGetComponent<CurrentTransport>(selectedEntity, out var component))
		{
			notifications = NotificationsSection.GetNotifications(base.EntityManager, component.m_CurrentTransport, notifications);
		}
		m_Dead = CitizenUtils.IsDead(base.EntityManager, selectedEntity);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = Visible();
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("happiness");
		if (m_Dead)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(happiness);
		}
		writer.PropertyName("conditions");
		if (m_Dead)
		{
			writer.WriteEmptyArray();
		}
		else
		{
			writer.ArrayBegin(conditions.Length);
			for (int i = 0; i < conditions.Length; i++)
			{
				writer.Write(conditions[i]);
			}
			writer.ArrayEnd();
		}
		writer.PropertyName("notifications");
		writer.ArrayBegin(notifications.Length);
		for (int j = 0; j < notifications.Length; j++)
		{
			Entity entity = notifications[j].entity;
			NotificationIconPrefab prefab = m_PrefabSystem.GetPrefab<NotificationIconPrefab>(entity);
			writer.TypeBegin("selectedInfo.NotificationData");
			writer.PropertyName("key");
			writer.Write(prefab.name);
			writer.PropertyName("iconPath");
			writer.Write(ImageSystem.GetIcon(prefab) ?? m_ImageSystem.placeholderIcon);
			writer.TypeEnd();
		}
		writer.ArrayEnd();
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		conditions.Clear();
		notifications.Clear();
		happiness = default(CitizenHappiness);
		m_Dead = false;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<Citizen>(selectedEntity))
		{
			return base.EntityManager.HasComponent<HouseholdMember>(selectedEntity);
		}
		return false;
	}
```


