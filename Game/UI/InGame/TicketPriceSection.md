# Game.UI.InGame.TicketPriceSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TicketPriceSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
    private Unity.Entities.Entity m_TicketPricePolicy;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Game.UI.InGame.UIPolicySlider <sliderData>k__BackingField;

    protected System.String group { protected get; }
    private Game.UI.InGame.UIPolicySlider sliderData { private get; private set; }

    public TicketPriceSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnProcess();
    private System.Void OnSetTicketPrice(System.Int32 newPrice);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  

```csharp
private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
```

- `private Unity.Entities.Entity m_TicketPricePolicy`  

```csharp
private Unity.Entities.Entity m_TicketPricePolicy;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Game.UI.InGame.UIPolicySlider <sliderData>k__BackingField`  

```csharp
private Game.UI.InGame.UIPolicySlider <sliderData>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.UI.InGame.UIPolicySlider sliderData { private get; private set }`  

```csharp
private Game.UI.InGame.UIPolicySlider sliderData { private get; private set; }
```


## Constructors

- `public TicketPriceSection()`  

```csharp
[Preserve]
	public TicketPriceSection()
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
		m_PoliciesUISystem = base.World.GetOrCreateSystemManaged<PoliciesUISystem>();
		m_ConfigQuery = GetEntityQuery(ComponentType.ReadOnly<UITransportConfigurationData>());
		AddBinding(new TriggerBinding<int>(group, "setTicketPrice", OnSetTicketPrice));
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		if (!m_ConfigQuery.IsEmptyIgnoreFilter)
		{
			UITransportConfigurationPrefab singletonPrefab = m_PrefabSystem.GetSingletonPrefab<UITransportConfigurationPrefab>(m_ConfigQuery);
			m_TicketPricePolicy = m_PrefabSystem.GetEntity(singletonPrefab.m_TicketPricePolicy);
		}
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		DynamicBuffer<Policy> buffer = base.EntityManager.GetBuffer<Policy>(selectedEntity, isReadOnly: true);
		PolicySliderData componentData = base.EntityManager.GetComponentData<PolicySliderData>(m_TicketPricePolicy);
		for (int i = 0; i < buffer.Length; i++)
		{
			if (!(buffer[i].m_Policy != m_TicketPricePolicy))
			{
				sliderData = new UIPolicySlider(((buffer[i].m_Flags & PolicyFlags.Active) != 0) ? buffer[i].m_Adjustment : 0f, componentData);
				return;
			}
		}
		sliderData = new UIPolicySlider(0f, componentData);
	}
```

- `private OnSetTicketPrice(System.Int32 newPrice) : System.Void`  

```csharp
private void OnSetTicketPrice(int newPrice)
	{
		m_PoliciesUISystem.SetPolicy(selectedEntity, m_TicketPricePolicy, newPrice > 0, Mathf.Clamp(newPrice, sliderData.range.min, sliderData.range.max));
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
		writer.PropertyName("sliderData");
		writer.Write(sliderData);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<Route>(selectedEntity) && base.EntityManager.HasComponent<TransportLine>(selectedEntity) && base.EntityManager.HasComponent<RouteWaypoint>(selectedEntity) && base.EntityManager.HasComponent<Policy>(selectedEntity) && base.EntityManager.TryGetComponent<TransportLineData>(selectedPrefab, out var component))
		{
			return !component.m_CargoTransport;
		}
		return false;
	}
```


