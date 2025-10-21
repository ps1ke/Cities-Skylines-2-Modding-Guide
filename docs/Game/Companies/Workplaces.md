# Game.Companies.Workplaces

**Assembly:** `Game`  
**Namespace:** `Game.Companies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.IAccumulable<Game.Companies.Workplaces>`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `DefaultMember`  

## Code

```csharp
public sealed struct Workplaces : Colossal.Collections.IAccumulable<Game.Companies.Workplaces>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Uneducated;
    public System.Int32 m_PoorlyEducated;
    public System.Int32 m_Educated;
    public System.Int32 m_WellEducated;
    public System.Int32 m_HighlyEducated;

    public System.Int32 TotalCount { get; }
    public System.Int32 SimpleWorkplacesCount { get; }
    public System.Int32 ComplexWorkplacesCount { get; }
    public System.Int32 Item { get; set; }

    public System.Void Accumulate(Game.Companies.Workplaces other);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void ToArray(Unity.Collections.NativeArray<System.Int32> array);
}
```


## Fields

- `public System.Int32 m_Uneducated`  

```csharp
public System.Int32 m_Uneducated;
```

- `public System.Int32 m_PoorlyEducated`  

```csharp
public System.Int32 m_PoorlyEducated;
```

- `public System.Int32 m_Educated`  

```csharp
public System.Int32 m_Educated;
```

- `public System.Int32 m_WellEducated`  

```csharp
public System.Int32 m_WellEducated;
```

- `public System.Int32 m_HighlyEducated`  

```csharp
public System.Int32 m_HighlyEducated;
```


## Properties

- `public System.Int32 TotalCount { get }`  

```csharp
public System.Int32 TotalCount { get; }
```

- `public System.Int32 SimpleWorkplacesCount { get }`  

```csharp
public System.Int32 SimpleWorkplacesCount { get; }
```

- `public System.Int32 ComplexWorkplacesCount { get }`  

```csharp
public System.Int32 ComplexWorkplacesCount { get; }
```

- `public System.Int32 Item { get; set }`  

```csharp
public System.Int32 Item { get; set; }
```


## Methods

- `public Accumulate(Game.Companies.Workplaces other) : System.Void`  

```csharp
public System.Void Accumulate(Game.Companies.Workplaces other);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public ToArray(Unity.Collections.NativeArray<System.Int32> array) : System.Void`  

```csharp
public System.Void ToArray(Unity.Collections.NativeArray<System.Int32> array);
```


