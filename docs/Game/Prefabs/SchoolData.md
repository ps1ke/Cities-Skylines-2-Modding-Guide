# Game.Prefabs.SchoolData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.SchoolData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct SchoolData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.SchoolData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_StudentCapacity;
    public System.Single m_GraduationModifier;
    public System.Byte m_EducationLevel;
    public System.SByte m_StudentWellbeing;
    public System.SByte m_StudentHealth;

    public System.Void Combine(Game.Prefabs.SchoolData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_StudentCapacity`  

```csharp
public System.Int32 m_StudentCapacity;
```

- `public System.Single m_GraduationModifier`  

```csharp
public System.Single m_GraduationModifier;
```

- `public System.Byte m_EducationLevel`  

```csharp
public System.Byte m_EducationLevel;
```

- `public System.SByte m_StudentWellbeing`  

```csharp
public System.SByte m_StudentWellbeing;
```

- `public System.SByte m_StudentHealth`  

```csharp
public System.SByte m_StudentHealth;
```


## Methods

- `public Combine(Game.Prefabs.SchoolData otherData) : System.Void`  

```csharp
public System.Void Combine(Game.Prefabs.SchoolData otherData);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


