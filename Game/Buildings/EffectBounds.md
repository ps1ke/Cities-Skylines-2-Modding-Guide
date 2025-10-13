# Game.Buildings.LocalEffectSystem+EffectBounds

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Buildings.LocalEffectSystem+EffectBounds>`, `Colossal.Mathematics.IBounds2<Game.Buildings.LocalEffectSystem+EffectBounds>`  

## Code

```csharp
public sealed struct EffectBounds : System.IEquatable<Game.Buildings.LocalEffectSystem+EffectBounds>, Colossal.Mathematics.IBounds2<Game.Buildings.LocalEffectSystem+EffectBounds>
{
    public Colossal.Mathematics.Bounds2 m_Bounds;
    public System.UInt32 m_TypeMask;
    public Unity.Mathematics.float2 m_Delta;

    public EffectBounds(Colossal.Mathematics.Bounds2 bounds, System.UInt32 typeMask, Unity.Mathematics.float2 delta);

    public Unity.Mathematics.float2 Center();
    public System.Boolean Equals(Game.Buildings.LocalEffectSystem+EffectBounds other);
    public System.Boolean Intersect(Game.Buildings.LocalEffectSystem+EffectBounds other);
    public Game.Buildings.LocalEffectSystem+EffectBounds Merge(Game.Buildings.LocalEffectSystem+EffectBounds other);
    public System.Void Reset();
    public Unity.Mathematics.float2 Size();
}
```


## Fields

- `public Colossal.Mathematics.Bounds2 m_Bounds`  

```csharp
public Colossal.Mathematics.Bounds2 m_Bounds;
```

- `public System.UInt32 m_TypeMask`  

```csharp
public System.UInt32 m_TypeMask;
```

- `public Unity.Mathematics.float2 m_Delta`  

```csharp
public Unity.Mathematics.float2 m_Delta;
```


## Constructors

- `public EffectBounds(Colossal.Mathematics.Bounds2 bounds, System.UInt32 typeMask, Unity.Mathematics.float2 delta)`  

```csharp
public EffectBounds(Colossal.Mathematics.Bounds2 bounds, System.UInt32 typeMask, Unity.Mathematics.float2 delta);
```


## Methods

- `public Center() : Unity.Mathematics.float2`  

```csharp
public Unity.Mathematics.float2 Center();
```

- `public Equals(Game.Buildings.LocalEffectSystem+EffectBounds other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Buildings.LocalEffectSystem+EffectBounds other);
```

- `public Intersect(Game.Buildings.LocalEffectSystem+EffectBounds other) : System.Boolean`  

```csharp
public System.Boolean Intersect(Game.Buildings.LocalEffectSystem+EffectBounds other);
```

- `public Merge(Game.Buildings.LocalEffectSystem+EffectBounds other) : Game.Buildings.LocalEffectSystem+EffectBounds`  

```csharp
public Game.Buildings.LocalEffectSystem+EffectBounds Merge(Game.Buildings.LocalEffectSystem+EffectBounds other);
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```

- `public Size() : Unity.Mathematics.float2`  

```csharp
public Unity.Mathematics.float2 Size();
```


