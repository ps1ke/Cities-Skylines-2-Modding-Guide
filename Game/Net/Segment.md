# Game.Net.Segment

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct Segment
{
    public Colossal.Mathematics.Bezier4x3 m_Left;
    public Colossal.Mathematics.Bezier4x3 m_Right;
    public Unity.Mathematics.float2 m_Length;

    public System.Single middleLength { get; }

}
```


## Fields

- `public Colossal.Mathematics.Bezier4x3 m_Left`  

```csharp
public Colossal.Mathematics.Bezier4x3 m_Left;
```

- `public Colossal.Mathematics.Bezier4x3 m_Right`  

```csharp
public Colossal.Mathematics.Bezier4x3 m_Right;
```

- `public Unity.Mathematics.float2 m_Length`  

```csharp
public Unity.Mathematics.float2 m_Length;
```


## Properties

- `public System.Single middleLength { get }`  

```csharp
public System.Single middleLength { get; }
```


