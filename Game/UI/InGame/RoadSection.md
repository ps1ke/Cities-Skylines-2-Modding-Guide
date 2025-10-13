# Game.UI.InGame.RoadSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RoadSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Single <length>k__BackingField;
    private System.Single <bestCondition>k__BackingField;
    private System.Single <worstCondition>k__BackingField;
    private System.Single <condition>k__BackingField;
    private System.Single <upkeep>k__BackingField;
    private System.Single[] m_Volume;
    private System.Single[] m_Flow;

    protected System.String group { protected get; }
    private System.Single length { private get; private set; }
    private System.Single bestCondition { private get; private set; }
    private System.Single worstCondition { private get; private set; }
    private System.Single condition { private get; private set; }
    private System.Single upkeep { private get; private set; }

    public RoadSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private System.Single <length>k__BackingField`  

```csharp
private System.Single <length>k__BackingField;
```

- `private System.Single <bestCondition>k__BackingField`  

```csharp
private System.Single <bestCondition>k__BackingField;
```

- `private System.Single <worstCondition>k__BackingField`  

```csharp
private System.Single <worstCondition>k__BackingField;
```

- `private System.Single <condition>k__BackingField`  

```csharp
private System.Single <condition>k__BackingField;
```

- `private System.Single <upkeep>k__BackingField`  

```csharp
private System.Single <upkeep>k__BackingField;
```

- `private System.Single[] m_Volume`  

```csharp
private System.Single[] m_Volume;
```

- `private System.Single[] m_Flow`  

```csharp
private System.Single[] m_Flow;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Single length { private get; private set }`  

```csharp
private System.Single length { private get; private set; }
```

- `private System.Single bestCondition { private get; private set }`  

```csharp
private System.Single bestCondition { private get; private set; }
```

- `private System.Single worstCondition { private get; private set }`  

```csharp
private System.Single worstCondition { private get; private set; }
```

- `private System.Single condition { private get; private set }`  

```csharp
private System.Single condition { private get; private set; }
```

- `private System.Single upkeep { private get; private set }`  

```csharp
private System.Single upkeep { private get; private set; }
```


## Constructors

- `public RoadSection()`  

```csharp
[Preserve]
	public RoadSection()
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
		m_Volume = new float[5];
		m_Flow = new float[5];
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		DynamicBuffer<AggregateElement> buffer = base.EntityManager.GetBuffer<AggregateElement>(selectedEntity, isReadOnly: true);
		for (int i = 0; i < buffer.Length; i++)
		{
			Entity edge = buffer[i].m_Edge;
			if (base.EntityManager.TryGetComponent<Road>(edge, out var component) && base.EntityManager.TryGetComponent<Curve>(edge, out var component2))
			{
				length += component2.m_Length;
				float4 @float = (component.m_TrafficFlowDistance0 + component.m_TrafficFlowDistance1) * 16f;
				float4 float2 = NetUtils.GetTrafficFlowSpeed(component) * 100f;
				m_Volume[0] += @float.x * 4f / 24f;
				m_Volume[1] += @float.y * 4f / 24f;
				m_Volume[2] += @float.z * 4f / 24f;
				m_Volume[3] += @float.w * 4f / 24f;
				m_Flow[0] += float2.x;
				m_Flow[1] += float2.y;
				m_Flow[2] += float2.z;
				m_Flow[3] += float2.w;
			}
			if (base.EntityManager.TryGetComponent<NetCondition>(edge, out var component3))
			{
				float2 wear = component3.m_Wear;
				if (wear.x > worstCondition)
				{
					worstCondition = wear.x;
				}
				if (wear.y > worstCondition)
				{
					worstCondition = wear.y;
				}
				if (wear.x < bestCondition)
				{
					bestCondition = wear.x;
				}
				if (wear.y < bestCondition)
				{
					bestCondition = wear.y;
				}
				condition += math.csum(wear) * 0.5f;
			}
			if (base.EntityManager.TryGetComponent<PrefabRef>(edge, out var component4) && base.EntityManager.TryGetComponent<PlaceableNetData>(component4.m_Prefab, out var component5))
			{
				upkeep += component5.m_DefaultUpkeepCost;
			}
		}
		m_Volume[0] /= buffer.Length;
		m_Volume[1] /= buffer.Length;
		m_Volume[2] /= buffer.Length;
		m_Volume[3] /= buffer.Length;
		m_Volume[4] = m_Volume[0];
		m_Flow[0] /= buffer.Length;
		m_Flow[1] /= buffer.Length;
		m_Flow[2] /= buffer.Length;
		m_Flow[3] /= buffer.Length;
		m_Flow[4] = m_Flow[0];
		bestCondition = 100f - bestCondition / 10f * 100f;
		worstCondition = 100f - worstCondition / 10f * 100f;
		condition = condition / 10f * 100f;
		condition = 100f - condition / (float)buffer.Length;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = base.EntityManager.HasComponent<Aggregate>(selectedEntity) && base.EntityManager.HasComponent<AggregateElement>(selectedEntity);
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("volumeData");
		writer.ArrayBegin(m_Volume.Length);
		for (int i = 0; i < m_Volume.Length; i++)
		{
			writer.Write(m_Volume[i]);
		}
		writer.ArrayEnd();
		writer.PropertyName("flowData");
		writer.ArrayBegin(m_Flow.Length);
		for (int j = 0; j < m_Flow.Length; j++)
		{
			writer.Write(m_Flow[j]);
		}
		writer.ArrayEnd();
		writer.PropertyName("length");
		writer.Write(length);
		writer.PropertyName("bestCondition");
		writer.Write(bestCondition);
		writer.PropertyName("worstCondition");
		writer.Write(worstCondition);
		writer.PropertyName("condition");
		writer.Write(condition);
		writer.PropertyName("upkeep");
		writer.Write(upkeep);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		for (int i = 0; i < 5; i++)
		{
			m_Volume[i] = 0f;
			m_Flow[i] = 0f;
		}
		length = 0f;
		bestCondition = 100f;
		worstCondition = 0f;
		condition = 0f;
		upkeep = 0f;
	}
```


