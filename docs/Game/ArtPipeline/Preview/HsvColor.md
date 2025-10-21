# Game.ArtPipeline.Preview.HsvColor

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct HsvColor
{
    public System.Double H;
    public System.Double S;
    public System.Double V;

    public System.Single normalizedH { get; set; }
    public System.Single normalizedS { get; set; }
    public System.Single normalizedV { get; set; }

    public HsvColor(System.Double h, System.Double s, System.Double v);

    public virtual System.String ToString();
}
```


## Fields

- `public System.Double H`  

```csharp
public System.Double H;
```

- `public System.Double S`  

```csharp
public System.Double S;
```

- `public System.Double V`  

```csharp
public System.Double V;
```


## Properties

- `public System.Single normalizedH { get; set }`  

```csharp
public System.Single normalizedH { get; set; }
```

- `public System.Single normalizedS { get; set }`  

```csharp
public System.Single normalizedS { get; set; }
```

- `public System.Single normalizedV { get; set }`  

```csharp
public System.Single normalizedV { get; set; }
```


## Constructors

- `public HsvColor(System.Double h, System.Double s, System.Double v)`  

```csharp
public HsvColor(System.Double h, System.Double s, System.Double v);
```


## Methods

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


