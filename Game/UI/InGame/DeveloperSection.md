# Game.UI.InGame.DeveloperSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.InGame.ISubsectionProvider`  

## Code

```csharp
public class DeveloperSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable, Game.UI.InGame.ISubsectionProvider
{
    private System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> <subsections>k__BackingField;

    protected System.String group { protected get; }
    public System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> subsections { get; private set; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForOutsideConnections { protected get; }
    protected System.Boolean displayForUnderConstruction { protected get; }
    protected System.Boolean displayForUpgrades { protected get; }

    public DeveloperSection();

    public System.Void AddSubsection(Game.UI.InGame.ISubsectionSource subsection);
    private System.Int32 GetSubsectionCount();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> <subsections>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> <subsections>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `public System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> subsections { get; private set }`  

```csharp
public System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> subsections { get; private set; }
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


## Constructors

- `public DeveloperSection()`  

```csharp
[Preserve]
	public DeveloperSection()
	{
	}
```


## Methods

- `public AddSubsection(Game.UI.InGame.ISubsectionSource subsection) : System.Void`  

```csharp
public void AddSubsection(ISubsectionSource subsection)
	{
		subsections.Add(subsection);
	}
```

- `private GetSubsectionCount() : System.Int32`  

```csharp
private int GetSubsectionCount()
	{
		int num = 0;
		for (int i = 0; i < subsections.Count; i++)
		{
			if (subsections[i].DisplayFor(selectedEntity, selectedPrefab))
			{
				num++;
			}
		}
		return num;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		subsections = new List<ISubsectionSource>();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		for (int i = 0; i < subsections.Count; i++)
		{
			if (subsections[i].DisplayFor(selectedEntity, selectedPrefab))
			{
				subsections[i].OnRequestUpdate(selectedEntity, selectedPrefab);
			}
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
		writer.PropertyName("subsections");
		writer.ArrayBegin(GetSubsectionCount());
		for (int i = 0; i < subsections.Count; i++)
		{
			if (subsections[i].DisplayFor(selectedEntity, selectedPrefab))
			{
				writer.Write(subsections[i]);
			}
		}
		writer.ArrayEnd();
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		bool result = false;
		for (int i = 0; i < subsections.Count; i++)
		{
			if (subsections[i].DisplayFor(selectedEntity, selectedPrefab))
			{
				result = true;
				break;
			}
		}
		return result;
	}
```


