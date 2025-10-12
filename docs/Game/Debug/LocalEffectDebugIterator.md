# Game.Debug.SearchTreeDebugSystem+LocalEffectDebugIterator

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds>`  

## Fields

- `private Colossal.Mathematics.Bounds2 m_Bounds`  
- `private Colossal.GizmoBatcher m_GizmoBatcher`  

## Constructors

- `public LocalEffectDebugIterator(Colossal.Mathematics.Bounds2 bounds, Colossal.GizmoBatcher gizmoBatcher)`  

## Methods

- `public Intersect(Game.Buildings.LocalEffectSystem+EffectBounds bounds) : System.Boolean`  
- `public Iterate(Game.Buildings.LocalEffectSystem+EffectBounds bounds, Game.Buildings.LocalEffectSystem+EffectItem item) : System.Void`  

