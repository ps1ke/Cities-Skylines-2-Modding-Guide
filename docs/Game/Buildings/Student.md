# Game.Buildings.Student

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`, `System.IEquatable<Game.Buildings.Student>`  

## Code

```csharp
public sealed struct Student : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable, System.IEquatable<Game.Buildings.Student>
{
    public Unity.Entities.Entity m_Student;

    public Student(Unity.Entities.Entity student);

    public System.Boolean Equals(Game.Buildings.Student other);
}
```


## Fields

- `public Unity.Entities.Entity m_Student`  

```csharp
public Unity.Entities.Entity m_Student;
```


## Constructors

- `public Student(Unity.Entities.Entity student)`  

```csharp
public Student(Unity.Entities.Entity student);
```


## Methods

- `public Equals(Game.Buildings.Student other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Buildings.Student other);
```


