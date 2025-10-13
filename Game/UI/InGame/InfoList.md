# Game.UI.InGame.InfoList

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.ISubsectionSource`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class InfoList : Game.UI.InGame.ISubsectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.String <label>k__BackingField;
    private System.Collections.Generic.List<Game.UI.InGame.InfoList+Item> <list>k__BackingField;
    private readonly System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> m_ShouldDisplay;
    private readonly System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.InfoList> m_OnUpdate;
    private System.Boolean <expanded>k__BackingField;

    public System.String label { get; set; }
    private System.Collections.Generic.List<Game.UI.InGame.InfoList+Item> list { private get; private set; }
    private System.Boolean expanded { private get; private set; }

    public InfoList(System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> shouldDisplay, System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.InfoList> onUpdate);

    public System.Void Add(Game.UI.InGame.InfoList+Item item);
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

- `private System.Collections.Generic.List<Game.UI.InGame.InfoList+Item> <list>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.InfoList+Item> <list>k__BackingField;
```

- `private readonly System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> m_ShouldDisplay`  

```csharp
private readonly System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> m_ShouldDisplay;
```

- `private readonly System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.InfoList> m_OnUpdate`  

```csharp
private readonly System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.InfoList> m_OnUpdate;
```

- `private System.Boolean <expanded>k__BackingField`  

```csharp
private System.Boolean <expanded>k__BackingField;
```


## Properties

- `public System.String label { get; set }`  

```csharp
public System.String label { get; set; }
```

- `private System.Collections.Generic.List<Game.UI.InGame.InfoList+Item> list { private get; private set }`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.InfoList+Item> list { private get; private set; }
```

- `private System.Boolean expanded { private get; private set }`  

```csharp
private System.Boolean expanded { private get; private set; }
```


## Constructors

- `public InfoList(System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> shouldDisplay, System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.InfoList> onUpdate)`  

```csharp
public InfoList(Func<Entity, Entity, bool> shouldDisplay, Action<Entity, Entity, InfoList> onUpdate)
	{
		list = new List<Item>();
		m_ShouldDisplay = shouldDisplay;
		m_OnUpdate = onUpdate;
	}
```


## Methods

- `public Add(Game.UI.InGame.InfoList+Item item) : System.Void`  

```csharp
public void Add(Item item)
	{
		list.Add(item);
	}
```

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
		list.Clear();
		m_OnUpdate(entity, prefab, this);
	}
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(GetType().FullName);
		writer.PropertyName("expanded");
		writer.Write(expanded);
		writer.PropertyName("label");
		writer.Write(label);
		writer.PropertyName("list");
		writer.ArrayBegin(list.Count);
		for (int i = 0; i < list.Count; i++)
		{
			writer.Write(list[i]);
		}
		writer.ArrayEnd();
		writer.TypeEnd();
	}
```


## Nested types

- `Game.UI.InGame.InfoList+Item`  

