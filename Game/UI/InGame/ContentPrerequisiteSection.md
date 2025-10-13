# Game.UI.InGame.ContentPrerequisiteSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class ContentPrerequisiteSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.String <contentPrefab>k__BackingField;

    private System.String contentPrefab { private get; private set; }
    protected System.Boolean displayForUpgrades { protected get; }
    protected System.Boolean displayForUnderConstruction { protected get; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForOutsideConnections { protected get; }
    protected System.String group { protected get; }

    public ContentPrerequisiteSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private System.String <contentPrefab>k__BackingField`  

```csharp
private System.String <contentPrefab>k__BackingField;
```


## Properties

- `private System.String contentPrefab { private get; private set }`  

```csharp
private System.String contentPrefab { private get; private set; }
```

- `protected System.Boolean displayForUpgrades { protected get }`  

```csharp
protected System.Boolean displayForUpgrades { protected get; }
```

- `protected System.Boolean displayForUnderConstruction { protected get }`  

```csharp
protected System.Boolean displayForUnderConstruction { protected get; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```

- `protected System.Boolean displayForOutsideConnections { protected get }`  

```csharp
protected System.Boolean displayForOutsideConnections { protected get; }
```

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```


## Constructors

- `public ContentPrerequisiteSection()`  

```csharp
[Preserve]
	public ContentPrerequisiteSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		if (base.EntityManager.TryGetComponent<ContentPrerequisiteData>(selectedPrefab, out var component))
		{
			contentPrefab = m_PrefabSystem.GetPrefabName(component.m_ContentPrerequisite);
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = base.EntityManager.TryGetComponent<ContentPrerequisiteData>(selectedPrefab, out var component) && !base.EntityManager.HasEnabledComponent<PrefabData>(component.m_ContentPrerequisite);
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("contentPrefab");
		writer.Write(contentPrefab);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		contentPrefab = string.Empty;
	}
```


