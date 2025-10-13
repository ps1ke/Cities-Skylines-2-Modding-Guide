# Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource>`  

## Code

```csharp
public sealed struct TopResource : System.IComparable<Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource>
{
    public System.String id;
    public System.Int32 amount;
    public UnityEngine.Color color;

    public TopResource(System.String id, System.Int32 amount, UnityEngine.Color color);

    public System.Int32 CompareTo(Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource other);
}
```


## Fields

- `public System.String id`  

```csharp
public System.String id;
```

- `public System.Int32 amount`  

```csharp
public System.Int32 amount;
```

- `public UnityEngine.Color color`  

```csharp
public UnityEngine.Color color;
```


## Constructors

- `public TopResource(System.String id, System.Int32 amount, UnityEngine.Color color)`  

```csharp
public TopResource(System.String id, System.Int32 amount, UnityEngine.Color color);
```


## Methods

- `public CompareTo(Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource other);
```


