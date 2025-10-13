# Game.Net.NodeColor

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IEmptySerializable`  

## Code

```csharp
public sealed struct NodeColor : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IEmptySerializable
{
    public System.Byte m_Index;
    public System.Byte m_Value;

    public NodeColor(System.Byte index, System.Byte value);

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


## Constructors

- `public NodeColor(System.Byte index, System.Byte value)`  

```csharp
public NodeColor(byte index, byte value)
	{
		m_Index = index;
		m_Value = value;
	}
```


