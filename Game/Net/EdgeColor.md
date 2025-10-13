# Game.Net.EdgeColor

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IEmptySerializable`  

## Code

```csharp
public sealed struct EdgeColor : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IEmptySerializable
{
    public System.Byte m_Index;
    public System.Byte m_Value0;
    public System.Byte m_Value1;

    public EdgeColor(System.Byte index, System.Byte value0, System.Byte value1);

}
```


## Fields

- `public System.Byte m_Index`  

```csharp
public System.Byte m_Index;
```

- `public System.Byte m_Value0`  

```csharp
public System.Byte m_Value0;
```

- `public System.Byte m_Value1`  

```csharp
public System.Byte m_Value1;
```


## Constructors

- `public EdgeColor(System.Byte index, System.Byte value0, System.Byte value1)`  

```csharp
public EdgeColor(byte index, byte value0, byte value1)
	{
		m_Index = index;
		m_Value0 = value0;
		m_Value1 = value1;
	}
```


