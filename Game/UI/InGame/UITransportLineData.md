# Game.UI.InGame.UITransportLineData

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `System.IComparable<Game.UI.InGame.UITransportLineData>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct UITransportLineData : Colossal.UI.Binding.IJsonWritable, System.IComparable<Game.UI.InGame.UITransportLineData>
{
    private readonly Unity.Entities.Entity <entity>k__BackingField;
    private readonly System.Boolean <active>k__BackingField;
    private readonly System.Boolean <visible>k__BackingField;
    private readonly System.Boolean <isCargo>k__BackingField;
    private readonly UnityEngine.Color32 <color>k__BackingField;
    private readonly System.Int32 <schedule>k__BackingField;
    private readonly Game.Prefabs.TransportType <type>k__BackingField;
    private readonly System.Single <length>k__BackingField;
    private readonly System.Int32 <stops>k__BackingField;
    private readonly System.Int32 <vehicles>k__BackingField;
    private readonly System.Int32 <cargo>k__BackingField;
    private readonly System.Single <usage>k__BackingField;

    public Unity.Entities.Entity entity { get; }
    public System.Boolean active { get; }
    public System.Boolean visible { get; }
    public System.Boolean isCargo { get; }
    public UnityEngine.Color32 color { get; }
    public System.Int32 schedule { get; }
    public Game.Prefabs.TransportType type { get; }
    public System.Single length { get; }
    public System.Int32 stops { get; }
    public System.Int32 vehicles { get; }
    public System.Int32 cargo { get; }
    public System.Single usage { get; }

    public UITransportLineData(Unity.Entities.Entity entity, System.Boolean active, System.Boolean visible, System.Boolean isCargo, Game.Routes.Color color, Game.UI.InGame.RouteSchedule schedule, Game.Prefabs.TransportType type, System.Single length, System.Int32 stops, System.Int32 vehicles, System.Int32 cargo, System.Single usage);

    public System.Int32 CompareTo(Game.UI.InGame.UITransportLineData other);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly Unity.Entities.Entity <entity>k__BackingField`  

```csharp
private readonly Unity.Entities.Entity <entity>k__BackingField;
```

- `private readonly System.Boolean <active>k__BackingField`  

```csharp
private readonly System.Boolean <active>k__BackingField;
```

- `private readonly System.Boolean <visible>k__BackingField`  

```csharp
private readonly System.Boolean <visible>k__BackingField;
```

- `private readonly System.Boolean <isCargo>k__BackingField`  

```csharp
private readonly System.Boolean <isCargo>k__BackingField;
```

- `private readonly UnityEngine.Color32 <color>k__BackingField`  

```csharp
private readonly UnityEngine.Color32 <color>k__BackingField;
```

- `private readonly System.Int32 <schedule>k__BackingField`  

```csharp
private readonly System.Int32 <schedule>k__BackingField;
```

- `private readonly Game.Prefabs.TransportType <type>k__BackingField`  

```csharp
private readonly Game.Prefabs.TransportType <type>k__BackingField;
```

- `private readonly System.Single <length>k__BackingField`  

```csharp
private readonly System.Single <length>k__BackingField;
```

- `private readonly System.Int32 <stops>k__BackingField`  

```csharp
private readonly System.Int32 <stops>k__BackingField;
```

- `private readonly System.Int32 <vehicles>k__BackingField`  

```csharp
private readonly System.Int32 <vehicles>k__BackingField;
```

- `private readonly System.Int32 <cargo>k__BackingField`  

```csharp
private readonly System.Int32 <cargo>k__BackingField;
```

- `private readonly System.Single <usage>k__BackingField`  

```csharp
private readonly System.Single <usage>k__BackingField;
```


## Properties

- `public Unity.Entities.Entity entity { get }`  

```csharp
public Unity.Entities.Entity entity { get; }
```

- `public System.Boolean active { get }`  

```csharp
public System.Boolean active { get; }
```

- `public System.Boolean visible { get }`  

```csharp
public System.Boolean visible { get; }
```

- `public System.Boolean isCargo { get }`  

```csharp
public System.Boolean isCargo { get; }
```

- `public UnityEngine.Color32 color { get }`  

```csharp
public UnityEngine.Color32 color { get; }
```

- `public System.Int32 schedule { get }`  

```csharp
public System.Int32 schedule { get; }
```

- `public Game.Prefabs.TransportType type { get }`  

```csharp
public Game.Prefabs.TransportType type { get; }
```

- `public System.Single length { get }`  

```csharp
public System.Single length { get; }
```

- `public System.Int32 stops { get }`  

```csharp
public System.Int32 stops { get; }
```

- `public System.Int32 vehicles { get }`  

```csharp
public System.Int32 vehicles { get; }
```

- `public System.Int32 cargo { get }`  

```csharp
public System.Int32 cargo { get; }
```

- `public System.Single usage { get }`  

```csharp
public System.Single usage { get; }
```


## Constructors

- `public UITransportLineData(Unity.Entities.Entity entity, System.Boolean active, System.Boolean visible, System.Boolean isCargo, Game.Routes.Color color, Game.UI.InGame.RouteSchedule schedule, Game.Prefabs.TransportType type, System.Single length, System.Int32 stops, System.Int32 vehicles, System.Int32 cargo, System.Single usage)`  

```csharp
public UITransportLineData(Entity entity, bool active, bool visible, bool isCargo, Game.Routes.Color color, RouteSchedule schedule, TransportType type, float length, int stops, int vehicles, int cargo, float usage)
	{
		this.entity = entity;
		this.active = active;
		this.visible = visible;
		this.isCargo = isCargo;
		this.color = color.m_Color;
		this.schedule = (int)schedule;
		this.type = type;
		this.length = length;
		this.stops = stops;
		this.vehicles = vehicles;
		this.cargo = cargo;
		this.usage = usage;
	}
```


## Methods

- `public CompareTo(Game.UI.InGame.UITransportLineData other) : System.Int32`  

```csharp
public int CompareTo(UITransportLineData other)
	{
		int num = type.CompareTo(other.type);
		if (num == 0)
		{
			return entity.Index.CompareTo(other.entity.Index);
		}
		return num;
	}
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(GetType().FullName);
		writer.PropertyName("entity");
		writer.Write(entity);
		writer.PropertyName("active");
		writer.Write(active);
		writer.PropertyName("visible");
		writer.Write(visible);
		writer.PropertyName("isCargo");
		writer.Write(isCargo);
		writer.PropertyName("color");
		writer.Write(color);
		writer.PropertyName("schedule");
		writer.Write(schedule);
		writer.PropertyName("type");
		writer.Write(Enum.GetName(typeof(TransportType), type));
		writer.PropertyName("length");
		writer.Write(length);
		writer.PropertyName("stops");
		writer.Write(stops);
		writer.PropertyName("vehicles");
		writer.Write(vehicles);
		writer.PropertyName("cargo");
		writer.Write(cargo);
		writer.PropertyName("usage");
		writer.Write(usage);
		writer.TypeEnd();
	}
```


