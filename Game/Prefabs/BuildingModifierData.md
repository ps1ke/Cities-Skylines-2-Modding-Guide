# Game.Prefabs.BuildingModifierData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct BuildingModifierData : Unity.Entities.IBufferElementData
{
    public Game.Buildings.BuildingModifierType m_Type;
    public Game.Prefabs.ModifierValueMode m_Mode;
    public Colossal.Mathematics.Bounds1 m_Range;

    public BuildingModifierData(Game.Buildings.BuildingModifierType type, Game.Prefabs.ModifierValueMode mode, Colossal.Mathematics.Bounds1 range);

}
```


## Fields

- `public Game.Buildings.BuildingModifierType m_Type`  

```csharp
public Game.Buildings.BuildingModifierType m_Type;
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

- `public BuildingModifierData(Game.Buildings.BuildingModifierType type, Game.Prefabs.ModifierValueMode mode, Colossal.Mathematics.Bounds1 range)`  

```csharp
public BuildingModifierData(BuildingModifierType type, ModifierValueMode mode, Bounds1 range)
	{
		m_Type = type;
		m_Mode = mode;
		m_Range = range;
	}
```


