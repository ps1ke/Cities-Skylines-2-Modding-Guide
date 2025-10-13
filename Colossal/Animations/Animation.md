# Colossal.Animations.Animation

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Animations`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct Animation
{
    public System.String name;
    public Colossal.Animations.AnimationType type;
    public Colossal.Animations.AnimationLayer layer;
    public System.Int32[] shapeIndices;
    public System.Int32[] boneIndices;
    public System.Int32 frameCount;
    public System.Int32 frameRate;
    public Unity.Mathematics.float3 positionMin;
    public Unity.Mathematics.float3 positionRange;
    public Colossal.Animations.Animation+Element[] elements;
    public System.Int32 elementsDiskDataSize;

    public Colossal.Animations.Animation+ElementRaw DecodeElement(System.Int32 index);
    public System.Void SetElements(System.ReadOnlySpan<Colossal.Animations.Animation+ElementRaw> input);
}
```


## Fields

- `public System.String name`  

```csharp
public System.String name;
```

- `public Colossal.Animations.AnimationType type`  

```csharp
public Colossal.Animations.AnimationType type;
```

- `public Colossal.Animations.AnimationLayer layer`  

```csharp
public Colossal.Animations.AnimationLayer layer;
```

- `public System.Int32[] shapeIndices`  

```csharp
public System.Int32[] shapeIndices;
```

- `public System.Int32[] boneIndices`  

```csharp
public System.Int32[] boneIndices;
```

- `public System.Int32 frameCount`  

```csharp
public System.Int32 frameCount;
```

- `public System.Int32 frameRate`  

```csharp
public System.Int32 frameRate;
```

- `public Unity.Mathematics.float3 positionMin`  

```csharp
public Unity.Mathematics.float3 positionMin;
```

- `public Unity.Mathematics.float3 positionRange`  

```csharp
public Unity.Mathematics.float3 positionRange;
```

- `public Colossal.Animations.Animation+Element[] elements`  

```csharp
public Colossal.Animations.Animation+Element[] elements;
```

- `public System.Int32 elementsDiskDataSize`  

```csharp
public System.Int32 elementsDiskDataSize;
```


## Methods

- `public DecodeElement(System.Int32 index) : Colossal.Animations.Animation+ElementRaw`  

```csharp
public Colossal.Animations.Animation+ElementRaw DecodeElement(System.Int32 index);
```

- `public SetElements(System.ReadOnlySpan<Colossal.Animations.Animation+ElementRaw> input) : System.Void`  

```csharp
public System.Void SetElements(System.ReadOnlySpan<Colossal.Animations.Animation+ElementRaw> input);
```


## Nested types

- `Colossal.Animations.Animation+Element`  
- `Colossal.Animations.Animation+ElementRaw`  

