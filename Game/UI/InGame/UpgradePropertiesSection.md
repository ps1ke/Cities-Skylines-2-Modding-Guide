# Game.UI.InGame.UpgradePropertiesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpgradePropertiesSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.Entity <mainBuilding>k__BackingField;
    private Unity.Entities.Entity <upgrade>k__BackingField;
    private Game.UI.InGame.UpgradePropertiesSection+UpgradeType <type>k__BackingField;
    private static readonly System.String kMainBuildingName;

    protected System.String group { protected get; }
    protected System.Boolean displayForUpgrades { protected get; }
    private Unity.Entities.Entity mainBuilding { private get; private set; }
    private Unity.Entities.Entity upgrade { private get; private set; }
    private Game.UI.InGame.UpgradePropertiesSection+UpgradeType type { private get; private set; }

    public UpgradePropertiesSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Entities.Entity <mainBuilding>k__BackingField`  

```csharp
private Unity.Entities.Entity <mainBuilding>k__BackingField;
```

- `private Unity.Entities.Entity <upgrade>k__BackingField`  

```csharp
private Unity.Entities.Entity <upgrade>k__BackingField;
```

- `private Game.UI.InGame.UpgradePropertiesSection+UpgradeType <type>k__BackingField`  

```csharp
private Game.UI.InGame.UpgradePropertiesSection+UpgradeType <type>k__BackingField;
```

- `private static readonly System.String kMainBuildingName`  

```csharp
private static readonly System.String kMainBuildingName;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `protected System.Boolean displayForUpgrades { protected get }`  

```csharp
protected System.Boolean displayForUpgrades { protected get; }
```

- `private Unity.Entities.Entity mainBuilding { private get; private set }`  

```csharp
private Unity.Entities.Entity mainBuilding { private get; private set; }
```

- `private Unity.Entities.Entity upgrade { private get; private set }`  

```csharp
private Unity.Entities.Entity upgrade { private get; private set; }
```

- `private Game.UI.InGame.UpgradePropertiesSection+UpgradeType type { private get; private set }`  

```csharp
private Game.UI.InGame.UpgradePropertiesSection+UpgradeType type { private get; private set; }
```


## Constructors

- `public UpgradePropertiesSection()`  

```csharp
[Preserve]
	public UpgradePropertiesSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		upgrade = selectedPrefab;
		if (base.EntityManager.TryGetComponent<Owner>(selectedEntity, out var component))
		{
			mainBuilding = component.m_Owner;
			if (base.EntityManager.TryGetComponent<Attachment>(mainBuilding, out var component2) && component2.m_Attached != Entity.Null)
			{
				mainBuilding = component2.m_Attached;
			}
		}
		type = (base.EntityManager.HasComponent<BuildingExtensionData>(selectedPrefab) ? UpgradeType.Extension : UpgradeType.SubBuilding);
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
		writer.PropertyName("mainBuilding");
		writer.Write(mainBuilding);
		writer.PropertyName(kMainBuildingName);
		m_NameSystem.BindName(writer, mainBuilding);
		writer.PropertyName("upgrade");
		writer.Write(upgrade);
		writer.PropertyName("type");
		writer.Write(type.ToString());
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		mainBuilding = Entity.Null;
		upgrade = Entity.Null;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		return base.EntityManager.HasComponent<ServiceUpgradeData>(selectedPrefab);
	}
```


## Nested types

- `Game.UI.InGame.UpgradePropertiesSection+UpgradeType`  

