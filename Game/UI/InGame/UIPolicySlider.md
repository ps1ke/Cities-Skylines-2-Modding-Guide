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
public UIPolicySlider(System.Single value, Game.Prefabs.PolicySliderData sliderData);
```

- `public UIPolicySlider(Game.Prefabs.PolicySliderData sliderData)`  

```csharp
public UIPolicySlider(Game.Prefabs.PolicySliderData sliderData);
```


## Methods

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public Equals(Game.UI.InGame.UIPolicySlider other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.UI.InGame.UIPolicySlider other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


