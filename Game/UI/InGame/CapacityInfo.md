# Game.UI.InGame.CapacityInfo

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.ISubsectionSource`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class CapacityInfo : Game.UI.InGame.ISubsectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.String <label>k__BackingField;
    private System.Int32 <value>k__BackingField;
    private System.Int32 <max>k__BackingField;
    private readonly System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> m_ShouldDisplay;
    private readonly System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.CapacityInfo> m_OnUpdate;

    public System.String label { get; set; }
    public System.Int32 value { get; set; }
    public System.Int32 max { get; set; }

    public CapacityInfo(System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> shouldDisplay, System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.CapacityInfo> onUpdate);

    public System.Boolean DisplayFor(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    public System.Void OnRequestUpdate(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String <label>k__BackingField`  

```csharp
private System.String <label>k__BackingField;
```

- `private System.Int32 <value>k__BackingField`  

```csharp
private System.Int32 <value>k__BackingField;
```

- `private System.Int32 <max>k__BackingField`  

```csharp
private System.Int32 <max>k__BackingField;
```

- `private readonly System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> m_ShouldDisplay`  

```csharp
private readonly System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> m_ShouldDisplay;
```

- `private readonly System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.CapacityInfo> m_OnUpdate`  

```csharp
private readonly System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.CapacityInfo> m_OnUpdate;
```


## Properties

- `public System.String label { get; set }`  

```csharp
public System.String label { get; set; }
```

- `public System.Int32 value { get; set }`  

```csharp
public System.Int32 value { get; set; }
```

- `public System.Int32 max { get; set }`  

```csharp
public System.Int32 max { get; set; }
```


## Constructors

- `public CapacityInfo(System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> shouldDisplay, System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.CapacityInfo> onUpdate)`  

```csharp
public CapacityInfo(Func<Entity, Entity, bool> shouldDisplay, Action<Entity, Entity, CapacityInfo> onUpdate)
	{
		m_ShouldDisplay = shouldDisplay;
		m_OnUpdate = onUpdate;
	}
```


## Methods

- `public DisplayFor(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
public bool DisplayFor(Entity entity, Entity prefab)
	{
		return m_ShouldDisplay(entity, prefab);
	}
```

- `public OnRequestUpdate(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Void`  

```csharp
public void OnRequestUpdate(Entity entity, Entity prefab)
	{
		m_OnUpdate(entity, prefab, this);
	}
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(GetType().FullName);
		writer.PropertyName("label");
		writer.Write(label);
		writer.PropertyName("value");
		writer.Write(value);
		writer.PropertyName("max");
		writer.Write(max);
		writer.TypeEnd();
	}
```


