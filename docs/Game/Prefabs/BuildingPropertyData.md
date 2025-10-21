# Game.Prefabs.BuildingPropertyData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct BuildingPropertyData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_ResidentialProperties;
    public Game.Economy.Resource m_AllowedSold;
    public Game.Economy.Resource m_AllowedInput;
    public Game.Economy.Resource m_AllowedManufactured;
    public Game.Economy.Resource m_AllowedStored;
    public System.Single m_SpaceMultiplier;

    public System.Int32 CountProperties(Game.Zones.AreaType areaType);
    public System.Int32 CountProperties();
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_ResidentialProperties`  

```csharp
public System.Int32 m_ResidentialProperties;
```

- `public Game.Economy.Resource m_AllowedSold`  

```csharp
public Game.Economy.Resource m_AllowedSold;
```

- `public Game.Economy.Resource m_AllowedInput`  

```csharp
public Game.Economy.Resource m_AllowedInput;
```

- `public Game.Economy.Resource m_AllowedManufactured`  

```csharp
public Game.Economy.Resource m_AllowedManufactured;
```

- `public Game.Economy.Resource m_AllowedStored`  

```csharp
public Game.Economy.Resource m_AllowedStored;
```

- `public System.Single m_SpaceMultiplier`  

```csharp
public System.Single m_SpaceMultiplier;
```


## Methods

- `public CountProperties(Game.Zones.AreaType areaType) : System.Int32`  

```csharp
public System.Int32 CountProperties(Game.Zones.AreaType areaType);
```

- `public CountProperties() : System.Int32`  

```csharp
public System.Int32 CountProperties();
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


