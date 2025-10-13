# Game.UI.InGame.EducationSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EducationSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <studentCount>k__BackingField;
    private System.Int32 <studentCapacity>k__BackingField;
    private System.Single <graduationTime>k__BackingField;
    private System.Single <failProbability>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 studentCount { private get; private set; }
    private System.Int32 studentCapacity { private get; private set; }
    private System.Single graduationTime { private get; private set; }
    private System.Single failProbability { private get; private set; }

    public EducationSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <studentCount>k__BackingField`  

```csharp
private System.Int32 <studentCount>k__BackingField;
```

- `private System.Int32 <studentCapacity>k__BackingField`  

```csharp
private System.Int32 <studentCapacity>k__BackingField;
```

- `private System.Single <graduationTime>k__BackingField`  

```csharp
private System.Single <graduationTime>k__BackingField;
```

- `private System.Single <failProbability>k__BackingField`  

```csharp
private System.Single <failProbability>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 studentCount { private get; private set }`  

```csharp
private System.Int32 studentCount { private get; private set; }
```

- `private System.Int32 studentCapacity { private get; private set }`  

```csharp
private System.Int32 studentCapacity { private get; private set; }
```

- `private System.Single graduationTime { private get; private set }`  

```csharp
private System.Single graduationTime { private get; private set; }
```

- `private System.Single failProbability { private get; private set }`  

```csharp
private System.Single failProbability { private get; private set; }
```


## Constructors

- `public EducationSection()`  

```csharp
[Preserve]
	public EducationSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		if (TryGetComponentWithUpgrades<SchoolData>(selectedEntity, selectedPrefab, out var data))
		{
			studentCapacity = data.m_StudentCapacity;
		}
		if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<Student> buffer))
		{
			studentCount = buffer.Length;
		}
		if (base.EntityManager.TryGetComponent<Game.Buildings.School>(selectedEntity, out var component))
		{
			graduationTime = ((component.m_AverageGraduationTime > 0f) ? component.m_AverageGraduationTime : 0.5f);
			failProbability = component.m_AverageFailProbability;
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
		writer.PropertyName("studentCount");
		writer.Write(studentCount);
		writer.PropertyName("studentCapacity");
		writer.Write(studentCapacity);
		writer.PropertyName("graduationTime");
		writer.Write(graduationTime);
		writer.PropertyName("failProbability");
		writer.Write(failProbability);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		studentCount = 0;
		studentCapacity = 0;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		return base.EntityManager.HasComponent<Game.Buildings.School>(selectedEntity);
	}
```


