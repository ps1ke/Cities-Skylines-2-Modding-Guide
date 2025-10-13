# Game.UI.InGame.TitleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TitleSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.ImageSystem m_ImageSystem;
    private System.String <icon>k__BackingField;

    protected System.String group { protected get; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForOutsideConnections { protected get; }
    protected System.Boolean displayForUnderConstruction { protected get; }
    protected System.Boolean displayForUpgrades { protected get; }
    private System.String icon { private get; private set; }

    public TitleSection();

    public static System.String GetVirtualKeyboardLocaleKey(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnProcess();
    private System.Void OnRename(System.String newName);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private System.String <icon>k__BackingField`  

```csharp
private System.String <icon>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```

- `protected System.Boolean displayForOutsideConnections { protected get }`  

```csharp
protected System.Boolean displayForOutsideConnections { protected get; }
```

- `protected System.Boolean displayForUnderConstruction { protected get }`  

```csharp
protected System.Boolean displayForUnderConstruction { protected get; }
```

- `protected System.Boolean displayForUpgrades { protected get }`  

```csharp
protected System.Boolean displayForUpgrades { protected get; }
```

- `private System.String icon { private get; private set }`  

```csharp
private System.String icon { private get; private set; }
```


## Constructors

- `public TitleSection()`  

```csharp
[Preserve]
	public TitleSection()
	{
	}
```


## Methods

- `public static GetVirtualKeyboardLocaleKey(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.String`  

```csharp
public static string GetVirtualKeyboardLocaleKey(EntityManager entityManager, Entity entity)
	{
		if (entityManager.HasComponent<Building>(entity))
		{
			return "BuildingName";
		}
		if (entityManager.HasComponent<Tree>(entity))
		{
			return "PlantName";
		}
		if (entityManager.HasComponent<Citizen>(entity))
		{
			return "CitizenName";
		}
		if (entityManager.HasComponent<Vehicle>(entity))
		{
			return "VehicleName";
		}
		if (entityManager.HasComponent<Animal>(entity))
		{
			return "AnimalName";
		}
		if (entityManager.HasComponent<TransportLine>(entity))
		{
			return "LineName";
		}
		if (entityManager.HasComponent<Aggregate>(entity))
		{
			return "RoadName";
		}
		if (entityManager.HasComponent<District>(entity))
		{
			return "DistrictName";
		}
		return "ObjectName";
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ImageSystem = base.World.GetOrCreateSystemManaged<ImageSystem>();
		AddBinding(new TriggerBinding<string>(group, "renameEntity", OnRename));
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		icon = m_ImageSystem.GetInstanceIcon(selectedEntity, selectedPrefab);
	}
```

- `private OnRename(System.String newName) : System.Void`  

```csharp
private void OnRename(string newName)
	{
		m_NameSystem.SetCustomName(selectedEntity, newName);
		m_InfoUISystem.RequestUpdate();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = selectedEntity != Entity.Null;
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("name");
		m_NameSystem.BindName(writer, selectedEntity);
		writer.PropertyName("vkName");
		m_NameSystem.BindNameForVirtualKeyboard(writer, selectedEntity);
		writer.PropertyName("vkLocaleKey");
		writer.Write(GetVirtualKeyboardLocaleKey(base.EntityManager, selectedEntity));
		writer.PropertyName("icon");
		if (icon == null)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(icon);
		}
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		icon = null;
	}
```


