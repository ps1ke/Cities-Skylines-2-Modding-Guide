# Game.UI.InGame.LoadSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class LoadSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Single <load>k__BackingField;
    private System.Single <capacity>k__BackingField;
    private Game.UI.InGame.LoadSection+LoadKey <loadKey>k__BackingField;

    protected System.String group { protected get; }
    private System.Single load { private get; private set; }
    private System.Single capacity { private get; private set; }
    private Game.UI.InGame.LoadSection+LoadKey loadKey { private get; private set; }
    protected Unity.Entities.Entity selectedEntity { protected get; }
    protected Unity.Entities.Entity selectedPrefab { protected get; }

    public LoadSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private System.Single <load>k__BackingField`  

```csharp
private System.Single <load>k__BackingField;
```

- `private System.Single <capacity>k__BackingField`  

```csharp
private System.Single <capacity>k__BackingField;
```

- `private Game.UI.InGame.LoadSection+LoadKey <loadKey>k__BackingField`  

```csharp
private Game.UI.InGame.LoadSection+LoadKey <loadKey>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Single load { private get; private set }`  

```csharp
private System.Single load { private get; private set; }
```

- `private System.Single capacity { private get; private set }`  

```csharp
private System.Single capacity { private get; private set; }
```

- `private Game.UI.InGame.LoadSection+LoadKey loadKey { private get; private set }`  

```csharp
private Game.UI.InGame.LoadSection+LoadKey loadKey { private get; private set; }
```

- `protected Unity.Entities.Entity selectedEntity { protected get }`  

```csharp
protected Unity.Entities.Entity selectedEntity { protected get; }
```

- `protected Unity.Entities.Entity selectedPrefab { protected get }`  

```csharp
protected Unity.Entities.Entity selectedPrefab { protected get; }
```


## Constructors

- `public LoadSection()`  

```csharp
[Preserve]
	public LoadSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		Game.Vehicles.GarbageTruck component2;
		Game.Vehicles.PostVan component3;
		if (base.EntityManager.TryGetComponent<Game.Vehicles.FireEngine>(selectedEntity, out var component))
		{
			load = component.m_ExtinguishingAmount;
			loadKey = LoadKey.Water;
		}
		else if (base.EntityManager.TryGetComponent<Game.Vehicles.GarbageTruck>(selectedEntity, out component2))
		{
			load = component2.m_Garbage;
			loadKey = (((component2.m_State & GarbageTruckFlags.IndustrialWasteOnly) != 0) ? LoadKey.IndustrialWaste : LoadKey.Garbage);
		}
		else if (base.EntityManager.TryGetComponent<Game.Vehicles.PostVan>(selectedEntity, out component3))
		{
			load = component3.m_DeliveringMail + component3.m_CollectedMail;
			loadKey = LoadKey.Mail;
		}
		base.tooltipKeys.Add(loadKey.ToString());
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		GarbageTruckData component2;
		PostVanData component3;
		if (base.EntityManager.TryGetComponent<FireEngineData>(selectedPrefab, out var component))
		{
			capacity = component.m_ExtinguishingCapacity;
		}
		else if (base.EntityManager.TryGetComponent<GarbageTruckData>(selectedPrefab, out component2))
		{
			capacity = component2.m_GarbageCapacity;
		}
		else if (base.EntityManager.TryGetComponent<PostVanData>(selectedPrefab, out component3))
		{
			capacity = component3.m_MailCapacity;
		}
		base.visible = capacity > 0f;
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("load");
		writer.Write(load);
		writer.PropertyName("capacity");
		writer.Write(capacity);
		writer.PropertyName("loadKey");
		writer.Write(Enum.GetName(typeof(LoadKey), loadKey));
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		loadKey = LoadKey.None;
		load = 0f;
		capacity = 0f;
	}
```


## Nested types

- `Game.UI.InGame.LoadSection+LoadKey`  

