# Game.UI.InGame.SewageSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SewageSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Single <capacity>k__BackingField;
    private System.Single <lastProcessed>k__BackingField;
    private System.Single <lastPurified>k__BackingField;
    private System.Single <purification>k__BackingField;

    protected System.String group { protected get; }
    private System.Single capacity { private get; private set; }
    private System.Single lastProcessed { private get; private set; }
    private System.Single lastPurified { private get; private set; }
    private System.Single purification { private get; private set; }

    public SewageSection();

    private System.Boolean HasWaterSource();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Single <capacity>k__BackingField`  

```csharp
private System.Single <capacity>k__BackingField;
```

- `private System.Single <lastProcessed>k__BackingField`  

```csharp
private System.Single <lastProcessed>k__BackingField;
```

- `private System.Single <lastPurified>k__BackingField`  

```csharp
private System.Single <lastPurified>k__BackingField;
```

- `private System.Single <purification>k__BackingField`  

```csharp
private System.Single <purification>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Single capacity { private get; private set }`  

```csharp
private System.Single capacity { private get; private set; }
```

- `private System.Single lastProcessed { private get; private set }`  

```csharp
private System.Single lastProcessed { private get; private set; }
```

- `private System.Single lastPurified { private get; private set }`  

```csharp
private System.Single lastPurified { private get; private set; }
```

- `private System.Single purification { private get; private set }`  

```csharp
private System.Single purification { private get; private set; }
```


## Constructors

- `public SewageSection()`  

```csharp
[Preserve]
	public SewageSection()
	{
	}
```


## Methods

- `private HasWaterSource() : System.Boolean`  

```csharp
private bool HasWaterSource()
	{
		if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<Game.Objects.SubObject> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				Entity subObject = buffer[i].m_SubObject;
				if (base.EntityManager.HasComponent<Game.Simulation.WaterSourceData>(subObject))
				{
					return true;
				}
			}
		}
		return false;
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		Game.Buildings.SewageOutlet componentData = base.EntityManager.GetComponentData<Game.Buildings.SewageOutlet>(selectedEntity);
		capacity = componentData.m_Capacity;
		lastProcessed = componentData.m_LastProcessed;
		lastPurified = componentData.m_LastPurified;
		if (TryGetComponentWithUpgrades<SewageOutletData>(selectedEntity, selectedPrefab, out var data))
		{
			purification = data.m_Purification;
		}
		base.tooltipKeys.Add(HasWaterSource() ? "Outlet" : "Treatment");
		if (purification > 0f)
		{
			if (base.EntityManager.HasComponent<Game.Buildings.WaterPumpingStation>(selectedEntity))
			{
				base.tooltipKeys.Add("TreatmentPurification");
			}
			else
			{
				base.tooltipKeys.Add("OutletPurification");
			}
		}
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
		writer.PropertyName("capacity");
		writer.Write(capacity);
		writer.PropertyName("lastProcessed");
		writer.Write(lastProcessed);
		writer.PropertyName("lastPurified");
		writer.Write(lastPurified);
		writer.PropertyName("purification");
		writer.Write(purification);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		capacity = 0f;
		lastProcessed = 0f;
		lastPurified = 0f;
		purification = 0f;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		return base.EntityManager.HasComponent<Game.Buildings.SewageOutlet>(selectedEntity);
	}
```


