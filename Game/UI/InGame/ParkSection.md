# Game.UI.InGame.ParkSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ParkSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <maintenance>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 maintenance { private get; private set; }

    public ParkSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <maintenance>k__BackingField`  

```csharp
private System.Int32 <maintenance>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 maintenance { private get; private set }`  

```csharp
private System.Int32 maintenance { private get; private set; }
```


## Constructors

- `public ParkSection()`  

```csharp
[Preserve]
	public ParkSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		if (TryGetComponentWithUpgrades<ParkData>(selectedEntity, selectedPrefab, out var data))
		{
			maintenance = Mathf.CeilToInt(math.select((float)base.EntityManager.GetComponentData<Game.Buildings.Park>(selectedEntity).m_Maintenance / (float)data.m_MaintenancePool, 0f, data.m_MaintenancePool == 0) * 100f);
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
		writer.PropertyName("maintenance");
		writer.Write(maintenance);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		maintenance = 0;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		return base.EntityManager.HasComponent<Game.Buildings.Park>(selectedEntity);
	}
```


