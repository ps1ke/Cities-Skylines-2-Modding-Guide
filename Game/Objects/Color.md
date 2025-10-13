# Game.Objects.Color

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IEmptySerializable`  

## Code

```csharp
public sealed struct Color : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IEmptySerializable
{
    public System.Byte m_Index;
    public System.Byte m_Value;
    public System.Boolean m_SubColor;

    public Color(System.Byte index, System.Byte value, System.Boolean subColor);

}
```


## Fields

- `public System.Byte m_Index`  

```csharp
public System.Byte m_Index;
```

- `public System.Byte m_Value`  

```csharp
public System.Byte m_Value;
```

- `public System.Boolean m_SubColor`  

```csharp
public System.Boolean m_SubColor;
```


## Constructors

- `public Color(System.Byte index, System.Byte value, System.Boolean subColor = False)`  

```csharp
public Color(System.Byte index, System.Byte value, System.Boolean subColor);
```


