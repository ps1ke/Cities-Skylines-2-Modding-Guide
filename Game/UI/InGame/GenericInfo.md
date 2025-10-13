# Game.UI.InGame.GenericInfo

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.ISubsectionSource`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class GenericInfo : Game.UI.InGame.ISubsectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.String <label>k__BackingField;
    private System.String <value>k__BackingField;
    private Unity.Entities.Entity <target>k__BackingField;
    private readonly System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> m_ShouldDisplay;
    private readonly System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.GenericInfo> m_OnUpdate;

    public System.String label { get; set; }
    public System.String value { get; set; }
    public Unity.Entities.Entity target { get; set; }

    public GenericInfo(System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> shouldDisplay, System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.GenericInfo> onUpdate);

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

- `private System.String <value>k__BackingField`  

```csharp
private System.String <value>k__BackingField;
```

- `private Unity.Entities.Entity <target>k__BackingField`  

```csharp
private Unity.Entities.Entity <target>k__BackingField;
```

- `private readonly System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> m_ShouldDisplay`  

```csharp
private readonly System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> m_ShouldDisplay;
```

- `private readonly System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.GenericInfo> m_OnUpdate`  

```csharp
private readonly System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.GenericInfo> m_OnUpdate;
```


## Properties

- `public System.String label { get; set }`  

```csharp
public System.String label { get; set; }
```

- `public System.String value { get; set }`  

```csharp
public System.String value { get; set; }
```

- `public Unity.Entities.Entity target { get; set }`  

```csharp
public Unity.Entities.Entity target { get; set; }
```


## Constructors

- `public GenericInfo(System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> shouldDisplay, System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.GenericInfo> onUpdate)`  

```csharp
public GenericInfo(Func<Entity, Entity, bool> shouldDisplay, Action<Entity, Entity, GenericInfo> onUpdate)
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
		writer.Write(label ?? string.Empty);
		writer.PropertyName("value");
		writer.Write(value ?? string.Empty);
		writer.PropertyName("target");
		if (target == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(target);
		}
		writer.TypeEnd();
	}
```


