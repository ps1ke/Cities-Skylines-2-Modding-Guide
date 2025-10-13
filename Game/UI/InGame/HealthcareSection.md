# Game.UI.InGame.HealthcareSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HealthcareSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <patientCount>k__BackingField;
    private System.Int32 <patientCapacity>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 patientCount { private get; private set; }
    private System.Int32 patientCapacity { private get; private set; }

    public HealthcareSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private System.Int32 <patientCount>k__BackingField`  

```csharp
private System.Int32 <patientCount>k__BackingField;
```

- `private System.Int32 <patientCapacity>k__BackingField`  

```csharp
private System.Int32 <patientCapacity>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 patientCount { private get; private set }`  

```csharp
private System.Int32 patientCount { private get; private set; }
```

- `private System.Int32 patientCapacity { private get; private set }`  

```csharp
private System.Int32 patientCapacity { private get; private set; }
```


## Constructors

- `public HealthcareSection()`  

```csharp
[Preserve]
	public HealthcareSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<Patient> buffer))
		{
			patientCount = buffer.Length;
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (base.EntityManager.HasComponent<Game.Buildings.Hospital>(selectedEntity) && TryGetComponentWithUpgrades<HospitalData>(selectedEntity, selectedPrefab, out var data))
		{
			patientCapacity = data.m_PatientCapacity;
		}
		base.visible = patientCapacity > 0;
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("patientCount");
		writer.Write(patientCount);
		writer.PropertyName("patientCapacity");
		writer.Write(patientCapacity);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		patientCount = 0;
		patientCapacity = 0;
	}
```


