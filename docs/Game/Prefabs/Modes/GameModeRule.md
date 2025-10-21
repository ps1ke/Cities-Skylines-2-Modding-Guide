# Game.Prefabs.Modes.GameModeRule

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Serializable`  

## Code

```csharp
public class GameModeRule
{
    public System.String m_Term;
    public System.String m_ArgName;
    public System.Int32 m_ArgValue;
    public Game.Prefabs.Modes.GameModeRule+ArgumentUnit m_ArgUnit;
    private static System.Collections.Generic.Dictionary<Game.Prefabs.Modes.GameModeRule+ArgumentUnit, System.String> kUnitDict;

    public GameModeRule();

    public System.String GetUnit();
}
```


## Fields

- `public System.String m_Term`  

```csharp
public System.String m_Term;
```

- `public System.String m_ArgName`  

```csharp
public System.String m_ArgName;
```

- `public System.Int32 m_ArgValue`  

```csharp
public System.Int32 m_ArgValue;
```

- `public Game.Prefabs.Modes.GameModeRule+ArgumentUnit m_ArgUnit`  

```csharp
public Game.Prefabs.Modes.GameModeRule+ArgumentUnit m_ArgUnit;
```

- `private static System.Collections.Generic.Dictionary<Game.Prefabs.Modes.GameModeRule+ArgumentUnit, System.String> kUnitDict`  

```csharp
private static System.Collections.Generic.Dictionary<Game.Prefabs.Modes.GameModeRule+ArgumentUnit, System.String> kUnitDict;
```


## Constructors

- `public GameModeRule()`  

```csharp
public GameModeRule();
```


## Methods

- `public GetUnit() : System.String`  

```csharp
public System.String GetUnit();
```


## Nested types

- `Game.Prefabs.Modes.GameModeRule+ArgumentUnit`  

