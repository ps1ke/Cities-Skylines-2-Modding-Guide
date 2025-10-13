# Game.Simulation.ZoneAmbiences

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ZoneAmbiences : Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_ResidentialLow;
    public System.Single m_CommercialLow;
    public System.Single m_Industrial;
    public System.Single m_Agriculture;
    public System.Single m_Forestry;
    public System.Single m_Oil;
    public System.Single m_Ore;
    public System.Single m_OfficeLow;
    public System.Single m_OfficeHigh;
    public System.Single m_ResidentialMedium;
    public System.Single m_ResidentialHigh;
    public System.Single m_ResidentialMixed;
    public System.Single m_CommercialHigh;
    public System.Single m_ResidentialLowRent;
    public System.Single m_Forest;
    public System.Single m_WaterfrontLow;
    public System.Single m_AquacultureLand;
    public System.Single m_SeagullAmbience;

    public System.Void AddAmbience(Game.Simulation.GroupAmbienceType type, System.Single value);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Single GetAmbience(Game.Simulation.GroupAmbienceType type);
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_ResidentialLow`  

```csharp
public System.Single m_ResidentialLow;
```

- `public System.Single m_CommercialLow`  

```csharp
public System.Single m_CommercialLow;
```

- `public System.Single m_Industrial`  

```csharp
public System.Single m_Industrial;
```

- `public System.Single m_Agriculture`  

```csharp
public System.Single m_Agriculture;
```

- `public System.Single m_Forestry`  

```csharp
public System.Single m_Forestry;
```

- `public System.Single m_Oil`  

```csharp
public System.Single m_Oil;
```

- `public System.Single m_Ore`  

```csharp
public System.Single m_Ore;
```

- `public System.Single m_OfficeLow`  

```csharp
public System.Single m_OfficeLow;
```

- `public System.Single m_OfficeHigh`  

```csharp
public System.Single m_OfficeHigh;
```

- `public System.Single m_ResidentialMedium`  

```csharp
public System.Single m_ResidentialMedium;
```

- `public System.Single m_ResidentialHigh`  

```csharp
public System.Single m_ResidentialHigh;
```

- `public System.Single m_ResidentialMixed`  

```csharp
public System.Single m_ResidentialMixed;
```

- `public System.Single m_CommercialHigh`  

```csharp
public System.Single m_CommercialHigh;
```

- `public System.Single m_ResidentialLowRent`  

```csharp
public System.Single m_ResidentialLowRent;
```

- `public System.Single m_Forest`  

```csharp
public System.Single m_Forest;
```

- `public System.Single m_WaterfrontLow`  

```csharp
public System.Single m_WaterfrontLow;
```

- `public System.Single m_AquacultureLand`  

```csharp
public System.Single m_AquacultureLand;
```

- `public System.Single m_SeagullAmbience`  

```csharp
public System.Single m_SeagullAmbience;
```


## Methods

- `public AddAmbience(Game.Simulation.GroupAmbienceType type, System.Single value) : System.Void`  

```csharp
public System.Void AddAmbience(Game.Simulation.GroupAmbienceType type, System.Single value);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetAmbience(Game.Simulation.GroupAmbienceType type) : System.Single`  

```csharp
public System.Single GetAmbience(Game.Simulation.GroupAmbienceType type);
```

- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  

```csharp
public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


