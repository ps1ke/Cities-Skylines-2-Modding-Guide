# Game.UI.InGame.HouseholdSidebarSection+HouseholdResult

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult>`, `System.IEquatable<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult>`  

## Code

```csharp
public sealed struct HouseholdResult : System.IComparable<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult>, System.IEquatable<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult>
{
    public Unity.Entities.Entity m_Entity;
    public System.Int32 m_Members;
    public System.Int32 m_Age;
    public System.Int32 m_Education;
    public System.Int32 m_Happiness;
    public System.Int32 m_Wealth;

    public System.Int32 CompareTo(Game.UI.InGame.HouseholdSidebarSection+HouseholdResult other);
    public System.Boolean Equals(Game.UI.InGame.HouseholdSidebarSection+HouseholdResult other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public System.Int32 m_Members`  

```csharp
public System.Int32 m_Members;
```

- `public System.Int32 m_Age`  

```csharp
public System.Int32 m_Age;
```

- `public System.Int32 m_Education`  

```csharp
public System.Int32 m_Education;
```

- `public System.Int32 m_Happiness`  

```csharp
public System.Int32 m_Happiness;
```

- `public System.Int32 m_Wealth`  

```csharp
public System.Int32 m_Wealth;
```


## Methods

- `public CompareTo(Game.UI.InGame.HouseholdSidebarSection+HouseholdResult other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.UI.InGame.HouseholdSidebarSection+HouseholdResult other);
```

- `public Equals(Game.UI.InGame.HouseholdSidebarSection+HouseholdResult other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.UI.InGame.HouseholdSidebarSection+HouseholdResult other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


