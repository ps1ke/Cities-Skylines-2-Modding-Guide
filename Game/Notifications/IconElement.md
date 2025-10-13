# Game.Notifications.IconElement

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Notifications.IconElement>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct IconElement : Unity.Entities.IBufferElementData, System.IEquatable<Game.Notifications.IconElement>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Icon;

    public IconElement(Unity.Entities.Entity icon);

    public System.Boolean Equals(Game.Notifications.IconElement other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Icon`  

```csharp
public Unity.Entities.Entity m_Icon;
```


## Constructors

- `public IconElement(Unity.Entities.Entity icon)`  

```csharp
public IconElement(Unity.Entities.Entity icon);
```


## Methods

- `public Equals(Game.Notifications.IconElement other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Notifications.IconElement other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


