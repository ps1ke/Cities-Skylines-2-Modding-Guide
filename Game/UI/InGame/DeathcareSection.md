# Game.UI.InGame.DeathcareSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DeathcareSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <bodyCount>k__BackingField;
    private System.Int32 <bodyCapacity>k__BackingField;
    private System.Single <processingSpeed>k__BackingField;
    private System.Single <processingCapacity>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 bodyCount { private get; private set; }
    private System.Int32 bodyCapacity { private get; private set; }
    private System.Single processingSpeed { private get; private set; }
    private System.Single processingCapacity { private get; private set; }

    public DeathcareSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <bodyCount>k__BackingField`  

```csharp
private System.Int32 <bodyCount>k__BackingField;
```

- `private System.Int32 <bodyCapacity>k__BackingField`  

```csharp
private System.Int32 <bodyCapacity>k__BackingField;
```

- `private System.Single <processingSpeed>k__BackingField`  

```csharp
private System.Single <processingSpeed>k__BackingField;
```

- `private System.Single <processingCapacity>k__BackingField`  

```csharp
private System.Single <processingCapacity>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 bodyCount { private get; private set }`  

```csharp
private System.Int32 bodyCount { private get; private set; }
```

- `private System.Int32 bodyCapacity { private get; private set }`  

```csharp
private System.Int32 bodyCapacity { private get; private set; }
```

- `private System.Single processingSpeed { private get; private set }`  

```csharp
private System.Single processingSpeed { private get; private set; }
```

- `private System.Single processingCapacity { private get; private set }`  

```csharp
private System.Single processingCapacity { private get; private set; }
```


## Constructors

- `public DeathcareSection()`  

```csharp
[Preserve]
	public DeathcareSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		if (TryGetComponentWithUpgrades<DeathcareFacilityData>(selectedEntity, selectedPrefab, out var data))
		{
			bodyCapacity = data.m_StorageCapacity;
			base.tooltipKeys.Add(data.m_LongTermStorage ? "Cemetery" : "Crematorium");
		}
		if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<Efficiency> buffer))
		{
			processingSpeed = data.m_ProcessingRate * BuildingUtils.GetEfficiency(buffer);
		}
		bodyCount = base.EntityManager.GetComponentData<Game.Buildings.DeathcareFacility>(selectedEntity).m_LongTermStoredCount;
		processingCapacity = data.m_ProcessingRate;
		if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<Patient> buffer2))
		{
			bodyCount += buffer2.Length;
		}
		if (bodyCount <= 0)
		{
			processingSpeed = 0f;
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
		writer.PropertyName("bodyCount");
		writer.Write(bodyCount);
		writer.PropertyName("bodyCapacity");
		writer.Write(bodyCapacity);
		writer.PropertyName("processingSpeed");
		writer.Write(processingSpeed);
		writer.PropertyName("processingCapacity");
		writer.Write(processingCapacity);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		bodyCount = 0;
		bodyCapacity = 0;
		processingSpeed = 0f;
		processingCapacity = 0f;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		return base.EntityManager.HasComponent<Game.Buildings.DeathcareFacility>(selectedEntity);
	}
```


