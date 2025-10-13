# Game.Pathfind.PathOwner

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PathOwner : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_ElementIndex;
    public Game.Pathfind.PathFlags m_State;

    public PathOwner(Game.Pathfind.PathFlags state);
    public PathOwner(System.Int32 elementIndex, Game.Pathfind.PathFlags state);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_ElementIndex`  

```csharp
public System.Int32 m_ElementIndex;
```

- `public Game.Pathfind.PathFlags m_State`  

```csharp
public Game.Pathfind.PathFlags m_State;
```


## Constructors

- `public PathOwner(Game.Pathfind.PathFlags state)`  

```csharp
public PathOwner(int elementIndex, PathFlags state)
	{
		m_ElementIndex = elementIndex;
		m_State = state;
	}
```

- `public PathOwner(System.Int32 elementIndex, Game.Pathfind.PathFlags state)`  

```csharp
public PathOwner(int elementIndex, PathFlags state)
	{
		m_ElementIndex = elementIndex;
		m_State = state;
	}
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


