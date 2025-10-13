# Game.UI.InGame.ShelterSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ShelterSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <sheltered>k__BackingField;
    private System.Int32 <shelterCapacity>k__BackingField;
    private System.Int32 <consumables>k__BackingField;
    private System.Int32 <consumableCapacity>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 sheltered { private get; private set; }
    private System.Int32 shelterCapacity { private get; private set; }
    private System.Int32 consumables { private get; private set; }
    private System.Int32 consumableCapacity { private get; private set; }

    public ShelterSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <sheltered>k__BackingField`  

```csharp
private System.Int32 <sheltered>k__BackingField;
```

- `private System.Int32 <shelterCapacity>k__BackingField`  

```csharp
private System.Int32 <shelterCapacity>k__BackingField;
```

- `private System.Int32 <consumables>k__BackingField`  

```csharp
private System.Int32 <consumables>k__BackingField;
```

- `private System.Int32 <consumableCapacity>k__BackingField`  

```csharp
private System.Int32 <consumableCapacity>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 sheltered { private get; private set }`  

```csharp
private System.Int32 sheltered { private get; private set; }
```

- `private System.Int32 shelterCapacity { private get; private set }`  

```csharp
private System.Int32 shelterCapacity { private get; private set; }
```

- `private System.Int32 consumables { private get; private set }`  

```csharp
private System.Int32 consumables { private get; private set; }
```

- `private System.Int32 consumableCapacity { private get; private set }`  

```csharp
private System.Int32 consumableCapacity { private get; private set; }
```


## Constructors

- `public ShelterSection()`  

```csharp
[Preserve]
	public ShelterSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		if (TryGetComponentWithUpgrades<EmergencyShelterData>(selectedEntity, selectedPrefab, out var data))
		{
			shelterCapacity = data.m_ShelterCapacity;
		}
		if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<Occupant> buffer))
		{
			sheltered = buffer.Length;
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
		writer.PropertyName("sheltered");
		writer.Write(sheltered);
		writer.PropertyName("shelterCapacity");
		writer.Write(shelterCapacity);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		sheltered = 0;
		shelterCapacity = 0;
		consumables = 0;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		return base.EntityManager.HasComponent<Game.Buildings.EmergencyShelter>(selectedEntity);
	}
```


