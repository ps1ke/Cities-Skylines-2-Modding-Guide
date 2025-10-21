# Game.Net.SubReplacement

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Net.SubReplacement>`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct SubReplacement : Unity.Entities.IBufferElementData, System.IEquatable<Game.Net.SubReplacement>, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Prefab;
    public Game.Net.SubReplacementType m_Type;
    public Game.Net.SubReplacementSide m_Side;
    public Game.Tools.AgeMask m_AgeMask;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Net.SubReplacement other);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```

- `public Game.Net.SubReplacementType m_Type`  

```csharp
public Game.Net.SubReplacementType m_Type;
```

- `public Game.Net.SubReplacementSide m_Side`  

```csharp
public Game.Net.SubReplacementSide m_Side;
```

- `public Game.Tools.AgeMask m_AgeMask`  

```csharp
public Game.Tools.AgeMask m_AgeMask;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Net.SubReplacement other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Net.SubReplacement other);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


