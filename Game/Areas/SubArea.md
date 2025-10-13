# Game.Areas.SubArea

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Areas.SubArea>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct SubArea : Unity.Entities.IBufferElementData, System.IEquatable<Game.Areas.SubArea>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Area;

    public SubArea(Unity.Entities.Entity area);

    public System.Boolean Equals(Game.Areas.SubArea other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Area`  

```csharp
public Unity.Entities.Entity m_Area;
```


## Constructors

- `public SubArea(Unity.Entities.Entity area)`  

```csharp
public SubArea(Unity.Entities.Entity area);
```


## Methods

- `public Equals(Game.Areas.SubArea other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Areas.SubArea other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


