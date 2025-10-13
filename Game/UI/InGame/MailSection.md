# Game.UI.InGame.MailSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MailSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <sortingRate>k__BackingField;
    private System.Int32 <sortingCapacity>k__BackingField;
    private System.Int32 <localAmount>k__BackingField;
    private System.Int32 <unsortedAmount>k__BackingField;
    private System.Int32 <outgoingAmount>k__BackingField;
    private System.Int32 <storedAmount>k__BackingField;
    private System.Int32 <storageCapacity>k__BackingField;
    private Game.UI.InGame.MailSection+MailKey <localKey>k__BackingField;
    private Game.UI.InGame.MailSection+MailKey <unsortedKey>k__BackingField;
    private Game.UI.InGame.MailSection+Type <type>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 sortingRate { private get; private set; }
    private System.Int32 sortingCapacity { private get; private set; }
    private System.Int32 localAmount { private get; private set; }
    private System.Int32 unsortedAmount { private get; private set; }
    private System.Int32 outgoingAmount { private get; private set; }
    private System.Int32 storedAmount { private get; private set; }
    private System.Int32 storageCapacity { private get; private set; }
    private Game.UI.InGame.MailSection+MailKey localKey { private get; private set; }
    private Game.UI.InGame.MailSection+MailKey unsortedKey { private get; private set; }
    private Game.UI.InGame.MailSection+Type type { private get; private set; }

    public MailSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <sortingRate>k__BackingField`  

```csharp
private System.Int32 <sortingRate>k__BackingField;
```

- `private System.Int32 <sortingCapacity>k__BackingField`  

```csharp
private System.Int32 <sortingCapacity>k__BackingField;
```

- `private System.Int32 <localAmount>k__BackingField`  

```csharp
private System.Int32 <localAmount>k__BackingField;
```

- `private System.Int32 <unsortedAmount>k__BackingField`  

```csharp
private System.Int32 <unsortedAmount>k__BackingField;
```

- `private System.Int32 <outgoingAmount>k__BackingField`  

```csharp
private System.Int32 <outgoingAmount>k__BackingField;
```

- `private System.Int32 <storedAmount>k__BackingField`  

```csharp
private System.Int32 <storedAmount>k__BackingField;
```

- `private System.Int32 <storageCapacity>k__BackingField`  

```csharp
private System.Int32 <storageCapacity>k__BackingField;
```

- `private Game.UI.InGame.MailSection+MailKey <localKey>k__BackingField`  

```csharp
private Game.UI.InGame.MailSection+MailKey <localKey>k__BackingField;
```

- `private Game.UI.InGame.MailSection+MailKey <unsortedKey>k__BackingField`  

```csharp
private Game.UI.InGame.MailSection+MailKey <unsortedKey>k__BackingField;
```

- `private Game.UI.InGame.MailSection+Type <type>k__BackingField`  

```csharp
private Game.UI.InGame.MailSection+Type <type>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 sortingRate { private get; private set }`  

```csharp
private System.Int32 sortingRate { private get; private set; }
```

- `private System.Int32 sortingCapacity { private get; private set }`  

```csharp
private System.Int32 sortingCapacity { private get; private set; }
```

- `private System.Int32 localAmount { private get; private set }`  

```csharp
private System.Int32 localAmount { private get; private set; }
```

- `private System.Int32 unsortedAmount { private get; private set }`  

```csharp
private System.Int32 unsortedAmount { private get; private set; }
```

- `private System.Int32 outgoingAmount { private get; private set }`  

```csharp
private System.Int32 outgoingAmount { private get; private set; }
```

- `private System.Int32 storedAmount { private get; private set }`  

```csharp
private System.Int32 storedAmount { private get; private set; }
```

- `private System.Int32 storageCapacity { private get; private set }`  

```csharp
private System.Int32 storageCapacity { private get; private set; }
```

- `private Game.UI.InGame.MailSection+MailKey localKey { private get; private set }`  

```csharp
private Game.UI.InGame.MailSection+MailKey localKey { private get; private set; }
```

- `private Game.UI.InGame.MailSection+MailKey unsortedKey { private get; private set }`  

```csharp
private Game.UI.InGame.MailSection+MailKey unsortedKey { private get; private set; }
```

- `private Game.UI.InGame.MailSection+Type type { private get; private set }`  

```csharp
private Game.UI.InGame.MailSection+Type type { private get; private set; }
```


## Constructors

- `public MailSection()`  

```csharp
[Preserve]
	public MailSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		Game.Routes.MailBox component2;
		MailBoxData component3;
		if (TryGetComponentWithUpgrades<PostFacilityData>(selectedEntity, selectedPrefab, out var data))
		{
			type = Type.PostFacility;
			Game.Buildings.PostFacility componentData = base.EntityManager.GetComponentData<Game.Buildings.PostFacility>(selectedEntity);
			sortingRate = (data.m_SortingRate * componentData.m_ProcessingFactor + 50) / 100;
			sortingCapacity = data.m_SortingRate;
			DynamicBuffer<Resources> buffer = base.EntityManager.GetBuffer<Resources>(selectedEntity, isReadOnly: true);
			unsortedAmount = EconomyUtils.GetResources(Resource.UnsortedMail, buffer);
			localAmount = EconomyUtils.GetResources(Resource.LocalMail, buffer);
			outgoingAmount = EconomyUtils.GetResources(Resource.OutgoingMail, buffer);
			if (base.EntityManager.TryGetComponent<Game.Routes.MailBox>(selectedEntity, out var component))
			{
				unsortedAmount += component.m_MailAmount;
			}
			localKey = ((data.m_PostVanCapacity <= 0) ? MailKey.Local : MailKey.ToDeliver);
			unsortedKey = ((data.m_PostVanCapacity > 0) ? MailKey.Collected : MailKey.Unsorted);
			storedAmount = unsortedAmount + localAmount + outgoingAmount;
			storageCapacity = data.m_MailCapacity;
			base.tooltipKeys.Add(localKey.ToString());
			if (sortingCapacity > 0 || outgoingAmount > 0)
			{
				base.tooltipKeys.Add("Outgoing");
			}
			base.tooltipKeys.Add(unsortedKey.ToString());
			if (sortingCapacity > 0)
			{
				base.tooltipKeys.Add("Sorting");
			}
			if (storageCapacity > 0)
			{
				base.tooltipKeys.Add("Storage");
			}
		}
		else if (base.EntityManager.TryGetComponent<Game.Routes.MailBox>(selectedEntity, out component2) && base.EntityManager.TryGetComponent<MailBoxData>(selectedPrefab, out component3))
		{
			type = Type.MailBox;
			storageCapacity = component3.m_MailCapacity;
			storedAmount = component2.m_MailAmount;
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
		writer.PropertyName("sortingRate");
		writer.Write(sortingRate);
		writer.PropertyName("sortingCapacity");
		writer.Write(sortingCapacity);
		writer.PropertyName("localAmount");
		writer.Write(localAmount);
		writer.PropertyName("unsortedAmount");
		writer.Write(unsortedAmount);
		writer.PropertyName("outgoingAmount");
		writer.Write(outgoingAmount);
		writer.PropertyName("storedAmount");
		writer.Write(storedAmount);
		writer.PropertyName("storageCapacity");
		writer.Write(storageCapacity);
		writer.PropertyName("localKey");
		writer.Write(Enum.GetName(typeof(MailKey), localKey));
		writer.PropertyName("unsortedKey");
		writer.Write(Enum.GetName(typeof(MailKey), unsortedKey));
		writer.PropertyName("type");
		writer.Write((int)type);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		sortingRate = 0;
		sortingCapacity = 0;
		localAmount = 0;
		unsortedAmount = 0;
		outgoingAmount = 0;
		storedAmount = 0;
		storageCapacity = 0;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (!base.EntityManager.HasComponent<Game.Buildings.PostFacility>(selectedEntity))
		{
			if (base.EntityManager.HasComponent<Game.Routes.MailBox>(selectedEntity))
			{
				return base.EntityManager.HasComponent<MailBoxData>(selectedPrefab);
			}
			return false;
		}
		return true;
	}
```


## Nested types

- `Game.UI.InGame.MailSection+MailKey`  
- `Game.UI.InGame.MailSection+Type`  

