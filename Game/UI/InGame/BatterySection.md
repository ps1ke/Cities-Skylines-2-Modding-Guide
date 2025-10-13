# Game.UI.InGame.BatterySection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BatterySection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <batteryCharge>k__BackingField;
    private System.Int32 <batteryCapacity>k__BackingField;
    private System.Int32 <flow>k__BackingField;
    private System.Single <remainingTime>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 batteryCharge { private get; private set; }
    private System.Int32 batteryCapacity { private get; private set; }
    private System.Int32 flow { private get; private set; }
    private System.Single remainingTime { private get; private set; }

    public BatterySection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <batteryCharge>k__BackingField`  

```csharp
private System.Int32 <batteryCharge>k__BackingField;
```

- `private System.Int32 <batteryCapacity>k__BackingField`  

```csharp
private System.Int32 <batteryCapacity>k__BackingField;
```

- `private System.Int32 <flow>k__BackingField`  

```csharp
private System.Int32 <flow>k__BackingField;
```

- `private System.Single <remainingTime>k__BackingField`  

```csharp
private System.Single <remainingTime>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 batteryCharge { private get; private set }`  

```csharp
private System.Int32 batteryCharge { private get; private set; }
```

- `private System.Int32 batteryCapacity { private get; private set }`  

```csharp
private System.Int32 batteryCapacity { private get; private set; }
```

- `private System.Int32 flow { private get; private set }`  

```csharp
private System.Int32 flow { private get; private set; }
```

- `private System.Single remainingTime { private get; private set }`  

```csharp
private System.Single remainingTime { private get; private set; }
```


## Constructors

- `public BatterySection()`  

```csharp
[Preserve]
	public BatterySection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		if (TryGetComponentWithUpgrades<BatteryData>(selectedEntity, selectedPrefab, out var data))
		{
			Game.Buildings.Battery componentData = base.EntityManager.GetComponentData<Game.Buildings.Battery>(selectedEntity);
			batteryCharge = componentData.storedEnergyHours;
			batteryCapacity = data.m_Capacity;
			flow = componentData.m_LastFlow;
			if (flow > 0)
			{
				long num = (data.capacityTicks - componentData.m_StoredEnergy) / flow;
				remainingTime = math.min((float)num / 2048f, 12f);
			}
			else if (flow < 0)
			{
				long num2 = componentData.m_StoredEnergy / -flow;
				remainingTime = math.min((float)num2 / 2048f, 12f);
			}
			else
			{
				remainingTime = 0f;
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
		writer.PropertyName("batteryCharge");
		writer.Write(batteryCharge);
		writer.PropertyName("batteryCapacity");
		writer.Write(batteryCapacity);
		writer.PropertyName("flow");
		writer.Write(flow);
		writer.PropertyName("remainingTime");
		writer.Write(remainingTime);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		batteryCharge = 0;
		batteryCapacity = 0;
		flow = 0;
		remainingTime = 0f;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		return base.EntityManager.HasComponent<Game.Buildings.Battery>(selectedEntity);
	}
```


