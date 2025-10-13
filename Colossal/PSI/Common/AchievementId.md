# Colossal.PSI.Common.AchievementId

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.PSI.Common.AchievementId>`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct AchievementId : System.IEquatable<Colossal.PSI.Common.AchievementId>
{
    public System.Int32 id;

    public AchievementId(System.Int32 id);

    public System.Boolean Equals(Colossal.PSI.Common.AchievementId other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public virtual System.String ToString();
}
```


## Fields

- `public System.Int32 id`  

```csharp
public System.Int32 id;
```


## Constructors

- `public AchievementId(System.Int32 id)`  

```csharp
public AchievementId(System.Int32 id);
```


## Methods

- `public Equals(Colossal.PSI.Common.AchievementId other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.PSI.Common.AchievementId other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


