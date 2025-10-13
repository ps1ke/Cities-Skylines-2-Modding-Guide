# Game.UI.InGame.HouseholdSidebarSection+ResidentResult

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.UI.InGame.HouseholdSidebarSection+ResidentResult>`, `System.IEquatable<Game.UI.InGame.HouseholdSidebarSection+ResidentResult>`  

## Code

```csharp
public sealed struct ResidentResult : System.IComparable<Game.UI.InGame.HouseholdSidebarSection+ResidentResult>, System.IEquatable<Game.UI.InGame.HouseholdSidebarSection+ResidentResult>
{
    public Unity.Entities.Entity m_Entity;
    public Game.Citizens.CitizenAge m_Age;
    public System.Int32 m_Education;
    public System.Int32 m_Happiness;

    public System.Int32 CompareTo(Game.UI.InGame.HouseholdSidebarSection+ResidentResult other);
    public System.Boolean Equals(Game.UI.InGame.HouseholdSidebarSection+ResidentResult other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public Game.Citizens.CitizenAge m_Age`  

```csharp
public Game.Citizens.CitizenAge m_Age;
```

- `public System.Int32 m_Education`  

```csharp
public System.Int32 m_Education;
```

- `public System.Int32 m_Happiness`  

```csharp
public System.Int32 m_Happiness;
```


## Methods

- `public CompareTo(Game.UI.InGame.HouseholdSidebarSection+ResidentResult other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.UI.InGame.HouseholdSidebarSection+ResidentResult other);
```

- `public Equals(Game.UI.InGame.HouseholdSidebarSection+ResidentResult other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.UI.InGame.HouseholdSidebarSection+ResidentResult other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


