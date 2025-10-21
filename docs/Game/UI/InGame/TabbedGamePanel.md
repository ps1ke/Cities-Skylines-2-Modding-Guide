# Game.UI.InGame.TabbedGamePanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `Game.UI.InGame.GamePanel`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `System.IEquatable<Game.UI.InGame.TabbedGamePanel>`  

## Code

```csharp
public abstract class TabbedGamePanel : Game.UI.InGame.GamePanel, Colossal.UI.Binding.IJsonWritable, System.IEquatable<Game.UI.InGame.TabbedGamePanel>
{
    private System.Int32 <selectedTab>k__BackingField;

    public System.Int32 selectedTab { get; set; }

    protected TabbedGamePanel();

    protected virtual System.Void BindProperties(Colossal.UI.Binding.IJsonWriter writer);
    public System.Boolean Equals(Game.UI.InGame.TabbedGamePanel other);
}
```


## Fields

- `private System.Int32 <selectedTab>k__BackingField`  

```csharp
private System.Int32 <selectedTab>k__BackingField;
```


## Properties

- `public System.Int32 selectedTab { get; set }`  

```csharp
public System.Int32 selectedTab { get; set; }
```


## Constructors

- `protected TabbedGamePanel()`  

```csharp
protected TabbedGamePanel();
```


## Methods

- `protected virtual BindProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void BindProperties(Colossal.UI.Binding.IJsonWriter writer);
```

- `public Equals(Game.UI.InGame.TabbedGamePanel other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.UI.InGame.TabbedGamePanel other);
```


