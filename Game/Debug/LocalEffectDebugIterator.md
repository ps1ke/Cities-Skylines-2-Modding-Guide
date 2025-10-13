# Game.Debug.SearchTreeDebugSystem+LocalEffectDebugIterator

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds>`  

## Code

```csharp
public sealed struct LocalEffectDebugIterator : Colossal.Collections.INativeQuadTreeIterator<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds>, Colossal.Collections.IUnsafeQuadTreeIterator<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds>
{
    private Colossal.Mathematics.Bounds2 m_Bounds;
    private Colossal.GizmoBatcher m_GizmoBatcher;

    public LocalEffectDebugIterator(Colossal.Mathematics.Bounds2 bounds, Colossal.GizmoBatcher gizmoBatcher);

    public System.Boolean Intersect(Game.Buildings.LocalEffectSystem+EffectBounds bounds);
    public System.Void Iterate(Game.Buildings.LocalEffectSystem+EffectBounds bounds, Game.Buildings.LocalEffectSystem+EffectItem item);
}
```


## Fields

- `private Colossal.Mathematics.Bounds2 m_Bounds`  

```csharp
private Colossal.Mathematics.Bounds2 m_Bounds;
```

- `private Colossal.GizmoBatcher m_GizmoBatcher`  

```csharp
private Colossal.GizmoBatcher m_GizmoBatcher;
```


## Constructors

- `public LocalEffectDebugIterator(Colossal.Mathematics.Bounds2 bounds, Colossal.GizmoBatcher gizmoBatcher)`  

```csharp
public LocalEffectDebugIterator(Colossal.Mathematics.Bounds2 bounds, Colossal.GizmoBatcher gizmoBatcher);
```


## Methods

- `public Intersect(Game.Buildings.LocalEffectSystem+EffectBounds bounds) : System.Boolean`  

```csharp
public System.Boolean Intersect(Game.Buildings.LocalEffectSystem+EffectBounds bounds);
```

- `public Iterate(Game.Buildings.LocalEffectSystem+EffectBounds bounds, Game.Buildings.LocalEffectSystem+EffectItem item) : System.Void`  

```csharp
public System.Void Iterate(Game.Buildings.LocalEffectSystem+EffectBounds bounds, Game.Buildings.LocalEffectSystem+EffectItem item);
```


