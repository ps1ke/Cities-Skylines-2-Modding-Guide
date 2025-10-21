# Game.Prefabs.LocalModifierData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct LocalModifierData : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Game.Buildings.LocalModifierType m_Type;
    public Game.Prefabs.ModifierValueMode m_Mode;
    public Game.Buildings.ModifierRadiusCombineMode m_RadiusCombineMode;
    public Colossal.Mathematics.Bounds1 m_Delta;
    public Colossal.Mathematics.Bounds1 m_Radius;

    public LocalModifierData(Game.Buildings.LocalModifierType type, Game.Prefabs.ModifierValueMode mode, Game.Buildings.ModifierRadiusCombineMode radiusMode, Colossal.Mathematics.Bounds1 delta, Colossal.Mathematics.Bounds1 radius);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Buildings.LocalModifierType m_Type`  

```csharp
public Game.Buildings.LocalModifierType m_Type;
```

- `public Game.Prefabs.ModifierValueMode m_Mode`  

```csharp
public Game.Prefabs.ModifierValueMode m_Mode;
```

- `public Game.Buildings.ModifierRadiusCombineMode m_RadiusCombineMode`  

```csharp
public Game.Buildings.ModifierRadiusCombineMode m_RadiusCombineMode;
```

- `public Colossal.Mathematics.Bounds1 m_Delta`  

```csharp
public Colossal.Mathematics.Bounds1 m_Delta;
```

- `public Colossal.Mathematics.Bounds1 m_Radius`  

```csharp
public Colossal.Mathematics.Bounds1 m_Radius;
```


## Constructors

- `public LocalModifierData(Game.Buildings.LocalModifierType type, Game.Prefabs.ModifierValueMode mode, Game.Buildings.ModifierRadiusCombineMode radiusMode, Colossal.Mathematics.Bounds1 delta, Colossal.Mathematics.Bounds1 radius)`  

```csharp
public LocalModifierData(Game.Buildings.LocalModifierType type, Game.Prefabs.ModifierValueMode mode, Game.Buildings.ModifierRadiusCombineMode radiusMode, Colossal.Mathematics.Bounds1 delta, Colossal.Mathematics.Bounds1 radius);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


