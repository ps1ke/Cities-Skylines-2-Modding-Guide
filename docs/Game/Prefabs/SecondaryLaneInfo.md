# Game.Prefabs.SecondaryLaneInfo

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Serializable`  

## Code

```csharp
public class SecondaryLaneInfo
{
    public Game.Prefabs.NetLanePrefab m_Lane;
    public System.Boolean m_RequireSafe;
    public System.Boolean m_RequireUnsafe;
    public System.Boolean m_RequireSingle;
    public System.Boolean m_RequireMultiple;
    public System.Boolean m_RequireAllowPassing;
    public System.Boolean m_RequireForbidPassing;
    public System.Boolean m_RequireMerge;
    public System.Boolean m_RequireContinue;
    public System.Boolean m_RequireSafeMaster;

    public SecondaryLaneInfo();

    public Game.Prefabs.SecondaryNetLaneFlags GetFlags();
}
```


## Fields

- `public Game.Prefabs.NetLanePrefab m_Lane`  

```csharp
public Game.Prefabs.NetLanePrefab m_Lane;
```

- `public System.Boolean m_RequireSafe`  

```csharp
public System.Boolean m_RequireSafe;
```

- `public System.Boolean m_RequireUnsafe`  

```csharp
public System.Boolean m_RequireUnsafe;
```

- `public System.Boolean m_RequireSingle`  

```csharp
public System.Boolean m_RequireSingle;
```

- `public System.Boolean m_RequireMultiple`  

```csharp
public System.Boolean m_RequireMultiple;
```

- `public System.Boolean m_RequireAllowPassing`  

```csharp
public System.Boolean m_RequireAllowPassing;
```

- `public System.Boolean m_RequireForbidPassing`  

```csharp
public System.Boolean m_RequireForbidPassing;
```

- `public System.Boolean m_RequireMerge`  

```csharp
public System.Boolean m_RequireMerge;
```

- `public System.Boolean m_RequireContinue`  

```csharp
public System.Boolean m_RequireContinue;
```

- `public System.Boolean m_RequireSafeMaster`  

```csharp
public System.Boolean m_RequireSafeMaster;
```


## Constructors

- `public SecondaryLaneInfo()`  

```csharp
public SecondaryLaneInfo();
```


## Methods

- `public GetFlags() : Game.Prefabs.SecondaryNetLaneFlags`  

```csharp
public Game.Prefabs.SecondaryNetLaneFlags GetFlags();
```


