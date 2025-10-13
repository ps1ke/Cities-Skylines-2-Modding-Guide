# Game.Rendering.ColorSet

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `DefaultMember`  

## Code

```csharp
public sealed struct ColorSet
{
    public UnityEngine.Color m_Channel0;
    public UnityEngine.Color m_Channel1;
    public UnityEngine.Color m_Channel2;

    public UnityEngine.Color Item { get; set; }

    public ColorSet(UnityEngine.Color color);

}
```


## Fields

- `public UnityEngine.Color m_Channel0`  

```csharp
public UnityEngine.Color m_Channel0;
```

- `public UnityEngine.Color m_Channel1`  

```csharp
public UnityEngine.Color m_Channel1;
```

- `public UnityEngine.Color m_Channel2`  

```csharp
public UnityEngine.Color m_Channel2;
```


## Properties

- `public UnityEngine.Color Item { get; set }`  

```csharp
public UnityEngine.Color Item { get; set; }
```


## Constructors

- `public ColorSet(UnityEngine.Color color)`  

```csharp
public ColorSet(Color color)
	{
		m_Channel0 = color;
		m_Channel1 = color;
		m_Channel2 = color;
	}
```


