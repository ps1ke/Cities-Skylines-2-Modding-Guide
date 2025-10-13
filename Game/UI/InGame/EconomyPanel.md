# Game.UI.InGame.EconomyPanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.TabbedGamePanel`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `System.IEquatable<Game.UI.InGame.TabbedGamePanel>`  

## Code

```csharp
public class EconomyPanel : Game.UI.InGame.TabbedGamePanel, Colossal.UI.Binding.IJsonWritable, System.IEquatable<Game.UI.InGame.TabbedGamePanel>
{
    public System.Boolean blocking { get; }
    public Game.UI.InGame.GamePanel+LayoutPosition position { get; }

    public EconomyPanel();

}
```


## Properties

- `public System.Boolean blocking { get }`  

```csharp
public System.Boolean blocking { get; }
```

- `public Game.UI.InGame.GamePanel+LayoutPosition position { get }`  

```csharp
public Game.UI.InGame.GamePanel+LayoutPosition position { get; }
```


## Constructors

- `public EconomyPanel()`  

```csharp
public EconomyPanel();
```


## Nested types

- `Game.UI.InGame.EconomyPanel+Tab`  

