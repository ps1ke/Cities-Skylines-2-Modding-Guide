# Game.Buildings.ExtractorFacility

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ExtractorFacility : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Buildings.ExtractorFlags m_Flags;
    public System.Byte m_Timer;
    public Game.Buildings.BuildingFlags m_MainBuildingFlags;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Buildings.ExtractorFlags m_Flags`  

```csharp
public Game.Buildings.ExtractorFlags m_Flags;
```

- `public System.Byte m_Timer`  

```csharp
public System.Byte m_Timer;
```

- `public Game.Buildings.BuildingFlags m_MainBuildingFlags`  

```csharp
public Game.Buildings.BuildingFlags m_MainBuildingFlags;
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


