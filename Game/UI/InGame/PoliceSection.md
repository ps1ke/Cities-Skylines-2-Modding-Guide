# Game.UI.InGame.PoliceSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PoliceSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <prisonerCount>k__BackingField;
    private System.Int32 <prisonerCapacity>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 prisonerCount { private get; private set; }
    private System.Int32 prisonerCapacity { private get; private set; }

    public PoliceSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <prisonerCount>k__BackingField`  

```csharp
private System.Int32 <prisonerCount>k__BackingField;
```

- `private System.Int32 <prisonerCapacity>k__BackingField`  

```csharp
private System.Int32 <prisonerCapacity>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 prisonerCount { private get; private set }`  

```csharp
private System.Int32 prisonerCount { private get; private set; }
```

- `private System.Int32 prisonerCapacity { private get; private set }`  

```csharp
private System.Int32 prisonerCapacity { private get; private set; }
```


## Constructors

- `public PoliceSection()`  

```csharp
[Preserve]
	public PoliceSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		if (TryGetComponentWithUpgrades<PoliceStationData>(selectedEntity, selectedPrefab, out var data))
		{
			prisonerCapacity = data.m_JailCapacity;
		}
		if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<Occupant> buffer))
		{
			prisonerCount = buffer.Length;
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
		writer.PropertyName("prisonerCount");
		writer.Write(prisonerCount);
		writer.PropertyName("prisonerCapacity");
		writer.Write(prisonerCapacity);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		prisonerCount = 0;
		prisonerCapacity = 0;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		return base.EntityManager.HasComponent<Game.Buildings.PoliceStation>(selectedEntity);
	}
```


