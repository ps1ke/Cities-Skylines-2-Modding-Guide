# Game.Rendering.InterpolatedTransform

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IEmptySerializable`  

## Code

```csharp
public sealed struct InterpolatedTransform : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.quaternion m_Rotation;
    public Game.Objects.TransformFlags m_Flags;

    public InterpolatedTransform(Game.Objects.Transform transform);
    public InterpolatedTransform(Game.Events.WeatherPhenomenon weatherPhenomenon);

    public Game.Objects.Transform ToTransform();
}
```


## Fields

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```

- `public Game.Objects.TransformFlags m_Flags`  

```csharp
public Game.Objects.TransformFlags m_Flags;
```


## Constructors

- `public InterpolatedTransform(Game.Objects.Transform transform)`  

```csharp
public InterpolatedTransform(Game.Objects.Transform transform);
```

- `public InterpolatedTransform(Game.Events.WeatherPhenomenon weatherPhenomenon)`  

```csharp
public InterpolatedTransform(Game.Events.WeatherPhenomenon weatherPhenomenon);
```


## Methods

- `public ToTransform() : Game.Objects.Transform`  

```csharp
public Game.Objects.Transform ToTransform();
```


