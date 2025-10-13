# Game.UI.Widgets.RangeNAttribute

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `UnityEngine.PropertyAttribute`  

## Code

```csharp
public class RangeNAttribute : UnityEngine.PropertyAttribute
{
    private Unity.Mathematics.float4 <min>k__BackingField;
    private Unity.Mathematics.float4 <max>k__BackingField;

    public Unity.Mathematics.float4 min { get; private set; }
    public Unity.Mathematics.float4 max { get; private set; }

    public RangeNAttribute(System.Single min, System.Single max, System.Boolean componentExpansion);
    public RangeNAttribute(Unity.Mathematics.float2 min, Unity.Mathematics.float2 max);
    public RangeNAttribute(Unity.Mathematics.float3 min, Unity.Mathematics.float3 max);
    public RangeNAttribute(Unity.Mathematics.float4 min, Unity.Mathematics.float4 max);

}
```


## Fields

- `private Unity.Mathematics.float4 <min>k__BackingField`  

```csharp
private Unity.Mathematics.float4 <min>k__BackingField;
```

- `private Unity.Mathematics.float4 <max>k__BackingField`  

```csharp
private Unity.Mathematics.float4 <max>k__BackingField;
```


## Properties

- `public Unity.Mathematics.float4 min { get; private set }`  

```csharp
public Unity.Mathematics.float4 min { get; private set; }
```

- `public Unity.Mathematics.float4 max { get; private set }`  

```csharp
public Unity.Mathematics.float4 max { get; private set; }
```


## Constructors

- `public RangeNAttribute(System.Single min, System.Single max, System.Boolean componentExpansion = True)`  

```csharp
public RangeNAttribute(System.Single min, System.Single max, System.Boolean componentExpansion);
```

- `public RangeNAttribute(Unity.Mathematics.float2 min, Unity.Mathematics.float2 max)`  

```csharp
public RangeNAttribute(Unity.Mathematics.float2 min, Unity.Mathematics.float2 max);
```

- `public RangeNAttribute(Unity.Mathematics.float3 min, Unity.Mathematics.float3 max)`  

```csharp
public RangeNAttribute(Unity.Mathematics.float3 min, Unity.Mathematics.float3 max);
```

- `public RangeNAttribute(Unity.Mathematics.float4 min, Unity.Mathematics.float4 max)`  

```csharp
public RangeNAttribute(Unity.Mathematics.float4 min, Unity.Mathematics.float4 max);
```


