# Game.Prefabs.InfomodeInfo

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IComparable<Game.Prefabs.InfomodeInfo>`  

**Attributes:** `Serializable`  

## Code

```csharp
public class InfomodeInfo : System.IComparable<Game.Prefabs.InfomodeInfo>
{
    public Game.Prefabs.InfomodePrefab m_Mode;
    public System.Int32 m_Priority;
    public System.Boolean m_Supplemental;
    public System.Boolean m_Optional;

    public InfomodeInfo();

    public System.Int32 CompareTo(Game.Prefabs.InfomodeInfo other);
}
```


## Fields

- `public Game.Prefabs.InfomodePrefab m_Mode`  

```csharp
public Game.Prefabs.InfomodePrefab m_Mode;
```

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```

- `public System.Boolean m_Supplemental`  

```csharp
public System.Boolean m_Supplemental;
```

- `public System.Boolean m_Optional`  

```csharp
public System.Boolean m_Optional;
```


## Constructors

- `public InfomodeInfo()`  

```csharp
public InfomodeInfo();
```


## Methods

- `public CompareTo(Game.Prefabs.InfomodeInfo other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Prefabs.InfomodeInfo other);
```


