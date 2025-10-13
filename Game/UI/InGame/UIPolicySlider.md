# Game.UI.InGame.UIPolicySlider

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.UI.InGame.UIPolicySlider>`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct UIPolicySlider : System.IEquatable<Game.UI.InGame.UIPolicySlider>, Colossal.UI.Binding.IJsonWritable
{
    private readonly System.Single m_Value;
    private readonly System.Single m_Default;
    private readonly System.Single m_Step;
    private readonly Game.Prefabs.PolicySliderUnit m_Unit;
    private readonly Colossal.Mathematics.Bounds1 <range>k__BackingField;

    public Colossal.Mathematics.Bounds1 range { get; }

    public UIPolicySlider(System.Single value, Game.Prefabs.PolicySliderData sliderData);
    public UIPolicySlider(Game.Prefabs.PolicySliderData sliderData);

    public virtual System.Boolean Equals(System.Object obj);
    public System.Boolean Equals(Game.UI.InGame.UIPolicySlider other);
    public virtual System.Int32 GetHashCode();
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly System.Single m_Value`  

```csharp
private readonly System.Single m_Value;
```

- `private readonly System.Single m_Default`  

```csharp
private readonly System.Single m_Default;
```

- `private readonly System.Single m_Step`  

```csharp
private readonly System.Single m_Step;
```

- `private readonly Game.Prefabs.PolicySliderUnit m_Unit`  

```csharp
private readonly Game.Prefabs.PolicySliderUnit m_Unit;
```

- `private readonly Colossal.Mathematics.Bounds1 <range>k__BackingField`  

```csharp
private readonly Colossal.Mathematics.Bounds1 <range>k__BackingField;
```


## Properties

- `public Colossal.Mathematics.Bounds1 range { get }`  

```csharp
public Colossal.Mathematics.Bounds1 range { get; }
```


## Constructors

- `public UIPolicySlider(System.Single value, Game.Prefabs.PolicySliderData sliderData)`  

```csharp
public UIPolicySlider(PolicySliderData sliderData)
	{
		m_Value = sliderData.m_Default;
		range = sliderData.m_Range;
		m_Default = sliderData.m_Default;
		m_Step = sliderData.m_Step;
		m_Unit = (PolicySliderUnit)sliderData.m_Unit;
	}
```

- `public UIPolicySlider(Game.Prefabs.PolicySliderData sliderData)`  

```csharp
public UIPolicySlider(PolicySliderData sliderData)
	{
		m_Value = sliderData.m_Default;
		range = sliderData.m_Range;
		m_Default = sliderData.m_Default;
		m_Step = sliderData.m_Step;
		m_Unit = (PolicySliderUnit)sliderData.m_Unit;
	}
```


## Methods

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public bool Equals(UIPolicySlider other)
	{
		Bounds1 bounds = range;
		float value = m_Value;
		float num = m_Default;
		float step = m_Step;
		PolicySliderUnit unit = m_Unit;
		Bounds1 bounds2 = other.range;
		float value2 = other.m_Value;
		float num2 = other.m_Default;
		float step2 = m_Step;
		PolicySliderUnit unit2 = m_Unit;
		if (bounds == bounds2 && value == value2 && num == num2 && step == step2)
		{
			return unit == unit2;
		}
		return false;
	}
```

- `public Equals(Game.UI.InGame.UIPolicySlider other) : System.Boolean`  

```csharp
public bool Equals(UIPolicySlider other)
	{
		Bounds1 bounds = range;
		float value = m_Value;
		float num = m_Default;
		float step = m_Step;
		PolicySliderUnit unit = m_Unit;
		Bounds1 bounds2 = other.range;
		float value2 = other.m_Value;
		float num2 = other.m_Default;
		float step2 = m_Step;
		PolicySliderUnit unit2 = m_Unit;
		if (bounds == bounds2 && value == value2 && num == num2 && step == step2)
		{
			return unit == unit2;
		}
		return false;
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return (range, m_Value, m_Default, m_Step, m_Unit).GetHashCode();
	}
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(TypeNames.kPolicySlider);
		writer.PropertyName("range");
		writer.Write(range);
		writer.PropertyName("value");
		writer.Write(m_Value);
		writer.PropertyName("default");
		writer.Write(m_Default);
		writer.PropertyName("step");
		writer.Write(m_Step);
		writer.PropertyName("unit");
		writer.Write(Enum.GetName(typeof(PolicySliderUnit), m_Unit));
		writer.TypeEnd();
	}
```


