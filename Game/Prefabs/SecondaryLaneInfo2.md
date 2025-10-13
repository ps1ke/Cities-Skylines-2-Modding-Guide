# Game.Prefabs.SecondaryLaneInfo2

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Serializable`  

## Code

```csharp
public class SecondaryLaneInfo2
{
    public Game.Prefabs.NetLanePrefab m_Lane;
    public System.Boolean m_RequireStop;
    public System.Boolean m_RequireYield;
    public System.Boolean m_RequirePavement;
    public System.Boolean m_RequireContinue;

    public SecondaryLaneInfo2();

    public Game.Prefabs.SecondaryNetLaneFlags GetFlags();
}
```


## Fields

- `public Game.Prefabs.NetLanePrefab m_Lane`  

```csharp
public Game.Prefabs.NetLanePrefab m_Lane;
```

- `public System.Boolean m_RequireStop`  

```csharp
public System.Boolean m_RequireStop;
```

- `public System.Boolean m_RequireYield`  

```csharp
public System.Boolean m_RequireYield;
```

- `public System.Boolean m_RequirePavement`  

```csharp
public System.Boolean m_RequirePavement;
```

- `public System.Boolean m_RequireContinue`  

```csharp
public System.Boolean m_RequireContinue;
```


## Constructors

- `public SecondaryLaneInfo2()`  

```csharp
public SecondaryLaneInfo2();
```


## Methods

- `public GetFlags() : Game.Prefabs.SecondaryNetLaneFlags`  

```csharp
public Game.Prefabs.SecondaryNetLaneFlags GetFlags();
```


