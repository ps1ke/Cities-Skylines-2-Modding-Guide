# Game.UI.InGame.UIPolicy

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.UI.InGame.UIPolicy>`, `System.IComparable<Game.UI.InGame.UIPolicy>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct UIPolicy : System.IEquatable<Game.UI.InGame.UIPolicy>, System.IComparable<Game.UI.InGame.UIPolicy>
{
    private readonly System.String m_Id;
    private readonly System.String m_LocalizedName;
    private readonly System.Int32 m_Priority;
    private readonly System.String m_Icon;
    private readonly Unity.Entities.Entity m_Entity;
    private readonly System.Boolean m_Locked;
    private readonly System.String m_UITag;
    private readonly System.Int32 m_Milestone;
    private readonly System.Boolean m_Active;
    private readonly System.Boolean m_Slider;
    private readonly Game.UI.InGame.UIPolicySlider m_Data;

    public UIPolicy(System.String id, System.String localizedName, System.Int32 priority, System.String icon, Unity.Entities.Entity entity, System.Boolean active, System.Boolean locked, System.String uiTag, System.Int32 milestone, System.Boolean slider, Game.UI.InGame.UIPolicySlider data);

    public System.Int32 CompareTo(Game.UI.InGame.UIPolicy other);
    public virtual System.Boolean Equals(System.Object obj);
    public System.Boolean Equals(Game.UI.InGame.UIPolicy other);
    public virtual System.Int32 GetHashCode();
    public System.Void Write(Game.UI.InGame.PrefabUISystem prefabUISystem, Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly System.String m_Id`  

```csharp
private readonly System.String m_Id;
```

- `private readonly System.String m_LocalizedName`  

```csharp
private readonly System.String m_LocalizedName;
```

- `private readonly System.Int32 m_Priority`  

```csharp
private readonly System.Int32 m_Priority;
```

- `private readonly System.String m_Icon`  

```csharp
private readonly System.String m_Icon;
```

- `private readonly Unity.Entities.Entity m_Entity`  

```csharp
private readonly Unity.Entities.Entity m_Entity;
```

- `private readonly System.Boolean m_Locked`  

```csharp
private readonly System.Boolean m_Locked;
```

- `private readonly System.String m_UITag`  

```csharp
private readonly System.String m_UITag;
```

- `private readonly System.Int32 m_Milestone`  

```csharp
private readonly System.Int32 m_Milestone;
```

- `private readonly System.Boolean m_Active`  

```csharp
private readonly System.Boolean m_Active;
```

- `private readonly System.Boolean m_Slider`  

```csharp
private readonly System.Boolean m_Slider;
```

- `private readonly Game.UI.InGame.UIPolicySlider m_Data`  

```csharp
private readonly Game.UI.InGame.UIPolicySlider m_Data;
```


## Constructors

- `public UIPolicy(System.String id, System.String localizedName, System.Int32 priority, System.String icon, Unity.Entities.Entity entity, System.Boolean active, System.Boolean locked, System.String uiTag, System.Int32 milestone, System.Boolean slider, Game.UI.InGame.UIPolicySlider data)`  

```csharp
public UIPolicy(string id, string localizedName, int priority, string icon, Entity entity, bool active, bool locked, string uiTag, int milestone, bool slider, UIPolicySlider data)
	{
		m_Id = id;
		m_LocalizedName = localizedName;
		m_Priority = priority;
		m_Icon = icon;
		m_Entity = entity;
		m_Active = active;
		m_Locked = locked;
		m_UITag = uiTag;
		m_Milestone = milestone;
		m_Slider = slider;
		m_Data = data;
	}
```


## Methods

- `public CompareTo(Game.UI.InGame.UIPolicy other) : System.Int32`  

```csharp
public int CompareTo(UIPolicy other)
	{
		int milestone = m_Milestone;
		int num = milestone.CompareTo(other.m_Milestone);
		milestone = m_Priority;
		int num2 = milestone.CompareTo(other.m_Priority);
		if (num == 0)
		{
			if (num2 == 0)
			{
				return string.Compare(m_LocalizedName, other.m_LocalizedName, StringComparison.Ordinal);
			}
			return num2;
		}
		return num;
	}
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public bool Equals(UIPolicy other)
	{
		return m_Entity == other.m_Entity;
	}
```

- `public Equals(Game.UI.InGame.UIPolicy other) : System.Boolean`  

```csharp
public bool Equals(UIPolicy other)
	{
		return m_Entity == other.m_Entity;
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return (m_Id, m_Icon, m_Entity, m_Active, m_Slider, m_Data).GetHashCode();
	}
```

- `public Write(Game.UI.InGame.PrefabUISystem prefabUISystem, Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(PrefabUISystem prefabUISystem, IJsonWriter writer)
	{
		writer.TypeBegin(TypeNames.kPolicy);
		writer.PropertyName("id");
		writer.Write(m_Id);
		writer.PropertyName("icon");
		writer.Write(m_Icon);
		writer.PropertyName("entity");
		if (m_Entity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(m_Entity);
		}
		writer.PropertyName("active");
		writer.Write(m_Active);
		writer.PropertyName("locked");
		writer.Write(m_Locked);
		writer.PropertyName("uiTag");
		writer.Write(m_UITag);
		writer.PropertyName("requirements");
		prefabUISystem.BindPrefabRequirements(writer, m_Entity);
		writer.PropertyName("data");
		if (m_Slider)
		{
			writer.Write(m_Data);
		}
		else
		{
			writer.WriteNull();
		}
		writer.TypeEnd();
	}
```


