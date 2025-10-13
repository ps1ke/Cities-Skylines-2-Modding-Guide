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
public UIPolicy(System.String id, System.String localizedName, System.Int32 priority, System.String icon, Unity.Entities.Entity entity, System.Boolean active, System.Boolean locked, System.String uiTag, System.Int32 milestone, System.Boolean slider, Game.UI.InGame.UIPolicySlider data);
```


## Methods

- `public CompareTo(Game.UI.InGame.UIPolicy other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.UI.InGame.UIPolicy other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public Equals(Game.UI.InGame.UIPolicy other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.UI.InGame.UIPolicy other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Write(Game.UI.InGame.PrefabUISystem prefabUISystem, Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Game.UI.InGame.PrefabUISystem prefabUISystem, Colossal.UI.Binding.IJsonWriter writer);
```


