# Game.Buildings.LocalEffectSystem+ReadData

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ReadData
{
    private Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds> m_SearchTree;

    public ReadData(Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds> searchTree);

    public System.Void ApplyModifier(System.Single& value, Unity.Mathematics.float3 position, Game.Buildings.LocalModifierType type);
}
```


## Fields

- `private Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds> m_SearchTree`  

```csharp
private Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds> m_SearchTree;
```


## Constructors

- `public ReadData(Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds> searchTree)`  

```csharp
public ReadData(Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds> searchTree);
```


## Methods

- `public ApplyModifier(System.Single& value, Unity.Mathematics.float3 position, Game.Buildings.LocalModifierType type) : System.Void`  

```csharp
public System.Void ApplyModifier(System.Single& value, Unity.Mathematics.float3 position, Game.Buildings.LocalModifierType type);
```


## Nested types

- `Game.Buildings.LocalEffectSystem+ReadData+Iterator`  

