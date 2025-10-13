# Game.UI.InGame.ElectricitySection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ElectricitySection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <capacity>k__BackingField;
    private System.Int32 <production>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 capacity { private get; private set; }
    private System.Int32 production { private get; private set; }

    public ElectricitySection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <capacity>k__BackingField`  

```csharp
private System.Int32 <capacity>k__BackingField;
```

- `private System.Int32 <production>k__BackingField`  

```csharp
private System.Int32 <production>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 capacity { private get; private set }`  

```csharp
private System.Int32 capacity { private get; private set; }
```

- `private System.Int32 production { private get; private set }`  

```csharp
private System.Int32 production { private get; private set; }
```


## Constructors

- `public ElectricitySection()`  

```csharp
[Preserve]
	public ElectricitySection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		ElectricityProducer componentData = base.EntityManager.GetComponentData<ElectricityProducer>(selectedEntity);
		capacity = componentData.m_Capacity;
		production = componentData.m_LastProduction;
		if (TryGetComponentWithUpgrades<SolarPoweredData>(selectedEntity, selectedPrefab, out var _))
		{
			base.tooltipKeys.Add("Solar");
		}
		if (TryGetComponentWithUpgrades<WindPoweredData>(selectedEntity, selectedPrefab, out var _))
		{
			base.tooltipKeys.Add("Wind");
		}
		if (TryGetComponentWithUpgrades<GarbagePoweredData>(selectedEntity, selectedPrefab, out var _))
		{
			base.tooltipKeys.Add("Garbage");
		}
		if (base.EntityManager.HasComponent<Game.Buildings.WaterPowered>(selectedEntity))
		{
			base.tooltipKeys.Add("Water");
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
		writer.PropertyName("production");
		writer.Write(production);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		capacity = 0;
		production = 0;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		return base.EntityManager.HasComponent<ElectricityProducer>(selectedEntity);
	}
```


