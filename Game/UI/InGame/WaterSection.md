# Game.UI.InGame.WaterSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Single <pollution>k__BackingField;
    private System.Int32 <capacity>k__BackingField;
    private System.Int32 <lastProduction>k__BackingField;

    protected System.String group { protected get; }
    private System.Single pollution { private get; private set; }
    private System.Int32 capacity { private get; private set; }
    private System.Int32 lastProduction { private get; private set; }

    public WaterSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Single <pollution>k__BackingField`  

```csharp
private System.Single <pollution>k__BackingField;
```

- `private System.Int32 <capacity>k__BackingField`  

```csharp
private System.Int32 <capacity>k__BackingField;
```

- `private System.Int32 <lastProduction>k__BackingField`  

```csharp
private System.Int32 <lastProduction>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Single pollution { private get; private set }`  

```csharp
private System.Single pollution { private get; private set; }
```

- `private System.Int32 capacity { private get; private set }`  

```csharp
private System.Int32 capacity { private get; private set; }
```

- `private System.Int32 lastProduction { private get; private set }`  

```csharp
private System.Int32 lastProduction { private get; private set; }
```


## Constructors

- `public WaterSection()`  

```csharp
[Preserve]
	public WaterSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		if (base.EntityManager.TryGetComponent<Game.Buildings.WaterPumpingStation>(selectedEntity, out var component))
		{
			pollution = component.m_Pollution;
			capacity = component.m_Capacity;
			lastProduction = component.m_LastProduction;
		}
		if (TryGetComponentWithUpgrades<WaterPumpingStationData>(selectedEntity, selectedPrefab, out var data) && data.m_Capacity > 0 && data.m_Types != AllowedWaterTypes.None)
		{
			base.tooltipKeys.Add("Pumping");
		}
		if ((double)pollution > 0.01)
		{
			base.tooltipKeys.Add("Pollution");
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
		writer.PropertyName("pollution");
		writer.Write(pollution);
		writer.PropertyName("capacity");
		writer.Write(capacity);
		writer.PropertyName("lastProduction");
		writer.Write(lastProduction);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		pollution = 0f;
		capacity = 0;
		lastProduction = 0;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		return base.EntityManager.HasComponent<Game.Buildings.WaterPumpingStation>(selectedEntity);
	}
```


