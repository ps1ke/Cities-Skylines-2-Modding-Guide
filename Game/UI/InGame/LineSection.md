# Game.UI.InGame.LineSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LineSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Single <length>k__BackingField;
    private System.Int32 <stops>k__BackingField;
    private System.Int32 <cargo>k__BackingField;
    private System.Single <usage>k__BackingField;

    protected System.String group { protected get; }
    private System.Single length { private get; private set; }
    private System.Int32 stops { private get; private set; }
    private System.Int32 cargo { private get; private set; }
    private System.Single usage { private get; private set; }

    public LineSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private System.Single <length>k__BackingField`  

```csharp
private System.Single <length>k__BackingField;
```

- `private System.Int32 <stops>k__BackingField`  

```csharp
private System.Int32 <stops>k__BackingField;
```

- `private System.Int32 <cargo>k__BackingField`  

```csharp
private System.Int32 <cargo>k__BackingField;
```

- `private System.Single <usage>k__BackingField`  

```csharp
private System.Single <usage>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Single length { private get; private set }`  

```csharp
private System.Single length { private get; private set; }
```

- `private System.Int32 stops { private get; private set }`  

```csharp
private System.Int32 stops { private get; private set; }
```

- `private System.Int32 cargo { private get; private set }`  

```csharp
private System.Int32 cargo { private get; private set; }
```

- `private System.Single usage { private get; private set }`  

```csharp
private System.Single usage { private get; private set; }
```


## Constructors

- `public LineSection()`  

```csharp
[Preserve]
	public LineSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		m_InfoUISystem.SetRoutesVisible();
		int num = 0;
		int capacity = 0;
		TransportUIUtils.GetRouteVehiclesCount(base.EntityManager, selectedEntity, ref num, ref capacity);
		usage = ((capacity > 0) ? ((float)num / (float)capacity) : 0f);
		stops = TransportUIUtils.GetStopCount(base.EntityManager, selectedEntity);
		length = TransportUIUtils.GetRouteLength(base.EntityManager, selectedEntity);
		cargo = num;
		base.tooltipTags.Add(TooltipTags.CargoRoute.ToString());
		base.tooltipTags.Add(TooltipTags.TransportLine.ToString());
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = base.EntityManager.HasComponent<Route>(selectedEntity) && base.EntityManager.HasComponent<TransportLine>(selectedEntity) && base.EntityManager.HasComponent<RouteWaypoint>(selectedEntity);
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("length");
		writer.Write(length);
		writer.PropertyName("stops");
		writer.Write(stops);
		writer.PropertyName("usage");
		writer.Write(usage);
		writer.PropertyName("cargo");
		writer.Write(cargo);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		length = 0f;
		stops = 0;
		cargo = 0;
		usage = 0f;
	}
```


