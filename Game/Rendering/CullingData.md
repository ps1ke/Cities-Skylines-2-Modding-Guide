# Game.Rendering.CullingData

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct CullingData
{
    public Colossal.Mathematics.Bounds3 m_Bounds;
    public System.UInt32 m_LodData1;
    public System.UInt32 m_LodData2;

    public Unity.Mathematics.int4 lodRange { get; set; }
    public Unity.Mathematics.int4 lodFade { get; set; }
    public System.Int32 lodOffset { get; set; }
    public System.Boolean isHidden { get; set; }
    public System.Boolean isFading { get; set; }

}
```


## Fields

- `public Colossal.Mathematics.Bounds3 m_Bounds`  

```csharp
public Colossal.Mathematics.Bounds3 m_Bounds;
```

- `public System.UInt32 m_LodData1`  

```csharp
public System.UInt32 m_LodData1;
```

- `public System.UInt32 m_LodData2`  

```csharp
public System.UInt32 m_LodData2;
```


## Properties

- `public Unity.Mathematics.int4 lodRange { get; set }`  

```csharp
public Unity.Mathematics.int4 lodRange { get; set; }
```

- `public Unity.Mathematics.int4 lodFade { get; set }`  

```csharp
public Unity.Mathematics.int4 lodFade { get; set; }
```

- `public System.Int32 lodOffset { get; set }`  

```csharp
public System.Int32 lodOffset { get; set; }
```

- `public System.Boolean isHidden { get; set }`  

```csharp
public System.Boolean isHidden { get; set; }
```

- `public System.Boolean isFading { get; set }`  

```csharp
public System.Boolean isFading { get; set; }
```


