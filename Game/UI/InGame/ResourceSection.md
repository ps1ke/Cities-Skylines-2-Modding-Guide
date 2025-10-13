# Game.UI.InGame.ResourceSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResourceSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Single <resourceAmount>k__BackingField;
    private Game.UI.InGame.ResourceSection+ResourceKey <resourceKey>k__BackingField;

    protected System.String group { protected get; }
    private System.Single resourceAmount { private get; private set; }
    private Game.UI.InGame.ResourceSection+ResourceKey resourceKey { private get; private set; }
    protected System.Boolean displayForDestroyedObjects { protected get; }

    public ResourceSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private System.Single <resourceAmount>k__BackingField`  

```csharp
private System.Single <resourceAmount>k__BackingField;
```

- `private Game.UI.InGame.ResourceSection+ResourceKey <resourceKey>k__BackingField`  

```csharp
private Game.UI.InGame.ResourceSection+ResourceKey <resourceKey>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Single resourceAmount { private get; private set }`  

```csharp
private System.Single resourceAmount { private get; private set; }
```

- `private Game.UI.InGame.ResourceSection+ResourceKey resourceKey { private get; private set }`  

```csharp
private Game.UI.InGame.ResourceSection+ResourceKey resourceKey { private get; private set; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```


## Constructors

- `public ResourceSection()`  

```csharp
[Preserve]
	public ResourceSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		Tree componentData = base.EntityManager.GetComponentData<Tree>(selectedEntity);
		Plant componentData2 = base.EntityManager.GetComponentData<Plant>(selectedEntity);
		TreeData componentData3 = base.EntityManager.GetComponentData<TreeData>(selectedPrefab);
		base.EntityManager.TryGetComponent<Damaged>(selectedEntity, out var component);
		resourceAmount = math.round(ObjectUtils.CalculateWoodAmount(componentData, componentData2, component, componentData3));
		resourceKey = ResourceKey.Wood;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = base.EntityManager.HasComponent<Tree>(selectedEntity) && base.EntityManager.TryGetComponent<TreeData>(selectedPrefab, out var component) && component.m_WoodAmount > 0f;
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("resourceAmount");
		writer.Write(resourceAmount);
		writer.PropertyName("resourceKey");
		writer.Write(Enum.GetName(typeof(ResourceKey), resourceKey));
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		resourceAmount = 0f;
	}
```


## Nested types

- `Game.UI.InGame.ResourceSection+ResourceKey`  

