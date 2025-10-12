# Game.Buildings.LocalEffectSystem+EffectBounds

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Buildings.LocalEffectSystem+EffectBounds>`, `Colossal.Mathematics.IBounds2<Game.Buildings.LocalEffectSystem+EffectBounds>`  

## Fields

- `public Colossal.Mathematics.Bounds2 m_Bounds`  
- `public System.UInt32 m_TypeMask`  
- `public Unity.Mathematics.float2 m_Delta`  

## Constructors

- `public EffectBounds(Colossal.Mathematics.Bounds2 bounds, System.UInt32 typeMask, Unity.Mathematics.float2 delta)`  

## Methods

- `public Center() : Unity.Mathematics.float2`  
- `public Equals(Game.Buildings.LocalEffectSystem+EffectBounds other) : System.Boolean`  
- `public Intersect(Game.Buildings.LocalEffectSystem+EffectBounds other) : System.Boolean`  
- `public Merge(Game.Buildings.LocalEffectSystem+EffectBounds other) : Game.Buildings.LocalEffectSystem+EffectBounds`  
- `public Reset() : System.Void`  
- `public Size() : Unity.Mathematics.float2`  

