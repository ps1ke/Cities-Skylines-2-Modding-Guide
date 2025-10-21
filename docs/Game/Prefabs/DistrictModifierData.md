# Game.Prefabs.DistrictModifierData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct DistrictModifierData : Unity.Entities.IBufferElementData
{
    public Game.Areas.DistrictModifierType m_Type;
    public Game.Prefabs.ModifierValueMode m_Mode;
    public Colossal.Mathematics.Bounds1 m_Range;

    public DistrictModifierData(Game.Areas.DistrictModifierType type, Game.Prefabs.ModifierValueMode mode, Colossal.Mathematics.Bounds1 range);

}
```


## Fields

- `public Game.Areas.DistrictModifierType m_Type`  

```csharp
public Game.Areas.DistrictModifierType m_Type;
```

- `public Game.Prefabs.ModifierValueMode m_Mode`  

```csharp
public Game.Prefabs.ModifierValueMode m_Mode;
```

- `public Colossal.Mathematics.Bounds1 m_Range`  

```csharp
public Colossal.Mathematics.Bounds1 m_Range;
```


## Constructors

- `public DistrictModifierData(Game.Areas.DistrictModifierType type, Game.Prefabs.ModifierValueMode mode, Colossal.Mathematics.Bounds1 range)`  

```csharp
public DistrictModifierData(Game.Areas.DistrictModifierType type, Game.Prefabs.ModifierValueMode mode, Colossal.Mathematics.Bounds1 range);
```


