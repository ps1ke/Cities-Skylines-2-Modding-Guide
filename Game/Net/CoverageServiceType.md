# Game.Net.CoverageServiceType

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.ISharedComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CoverageServiceType : Unity.Entities.ISharedComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Net.CoverageService m_Service;

    public CoverageServiceType(Game.Net.CoverageService service);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Net.CoverageService m_Service`  

```csharp
public Game.Net.CoverageService m_Service;
```


## Constructors

- `public CoverageServiceType(Game.Net.CoverageService service)`  

```csharp
public CoverageServiceType(CoverageService service)
	{
		m_Service = service;
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


