# Game.UI.InGame.ComfortSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ComfortSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <comfort>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 comfort { private get; private set; }

    public ComfortSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <comfort>k__BackingField`  

```csharp
private System.Int32 <comfort>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 comfort { private get; private set }`  

```csharp
private System.Int32 comfort { private get; private set; }
```


## Constructors

- `public ComfortSection()`  

```csharp
[Preserve]
	public ComfortSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		float num = 0f;
		TransportStation component2;
		ParkingFacility component3;
		if (base.EntityManager.TryGetComponent<TransportStop>(selectedEntity, out var component))
		{
			num = component.m_ComfortFactor;
			base.tooltipKeys.Add("TransportStop");
		}
		else if (base.EntityManager.TryGetComponent<TransportStation>(selectedEntity, out component2))
		{
			num = component2.m_ComfortFactor;
			base.tooltipKeys.Add("TransportStation");
		}
		else if (base.EntityManager.TryGetComponent<ParkingFacility>(selectedEntity, out component3))
		{
			num = component3.m_ComfortFactor;
			base.tooltipKeys.Add("Parking");
		}
		comfort = (int)math.round(100f * num);
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
		writer.PropertyName("comfort");
		writer.Write(comfort);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		comfort = 0;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if ((base.EntityManager.HasComponent<MailBox>(selectedEntity) || !base.EntityManager.HasComponent<TransportStop>(selectedEntity)) && (!base.EntityManager.HasComponent<TransportStation>(selectedEntity) || !base.EntityManager.HasComponent<PublicTransportStation>(selectedEntity)))
		{
			return base.EntityManager.HasComponent<ParkingFacility>(selectedEntity);
		}
		return true;
	}
```


