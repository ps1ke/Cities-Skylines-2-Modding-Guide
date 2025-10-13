# Game.Prefabs.AdditionalBuildingTerraformElement

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct AdditionalBuildingTerraformElement : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Colossal.Mathematics.Bounds2 m_Area;
    public System.Single m_HeightOffset;
    public System.Boolean m_Circular;
    public System.Boolean m_DontRaise;
    public System.Boolean m_DontLower;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Colossal.Mathematics.Bounds2 m_Area`  

```csharp
public Colossal.Mathematics.Bounds2 m_Area;
```

- `public System.Single m_HeightOffset`  

```csharp
public System.Single m_HeightOffset;
```

- `public System.Boolean m_Circular`  

```csharp
public System.Boolean m_Circular;
```

- `public System.Boolean m_DontRaise`  

```csharp
public System.Boolean m_DontRaise;
```

- `public System.Boolean m_DontLower`  

```csharp
public System.Boolean m_DontLower;
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


