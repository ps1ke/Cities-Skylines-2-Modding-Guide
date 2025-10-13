# Game.Prefabs.CityModifierData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct CityModifierData : Unity.Entities.IBufferElementData
{
    public Game.City.CityModifierType m_Type;
    public Game.Prefabs.ModifierValueMode m_Mode;
    public Colossal.Mathematics.Bounds1 m_Range;

    public CityModifierData(Game.City.CityModifierType type, Game.Prefabs.ModifierValueMode mode, Colossal.Mathematics.Bounds1 range);

}
```


## Fields

- `public Game.City.CityModifierType m_Type`  

```csharp
public Game.City.CityModifierType m_Type;
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

- `public CityModifierData(Game.City.CityModifierType type, Game.Prefabs.ModifierValueMode mode, Colossal.Mathematics.Bounds1 range)`  

```csharp
public CityModifierData(CityModifierType type, ModifierValueMode mode, Bounds1 range)
	{
		m_Type = type;
		m_Mode = mode;
		m_Range = range;
	}
```


