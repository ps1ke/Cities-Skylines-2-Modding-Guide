# Game.UI.InGame.GamePanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public abstract class GamePanel : Colossal.UI.Binding.IJsonWritable
{
    public System.Boolean blocking { get; }
    public System.Boolean retainSelection { get; }
    public System.Boolean retainProperties { get; }
    public Game.UI.InGame.GamePanel+LayoutPosition position { get; }

    protected GamePanel();

    protected virtual System.Void BindProperties(Colossal.UI.Binding.IJsonWriter writer);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Properties

- `public System.Boolean blocking { get }`  

```csharp
public System.Boolean blocking { get; }
```

- `public System.Boolean retainSelection { get }`  

```csharp
public System.Boolean retainSelection { get; }
```

- `public System.Boolean retainProperties { get }`  

```csharp
public System.Boolean retainProperties { get; }
```

- `public Game.UI.InGame.GamePanel+LayoutPosition position { get }`  

```csharp
public Game.UI.InGame.GamePanel+LayoutPosition position { get; }
```


## Constructors

- `protected GamePanel()`  

```csharp
protected GamePanel();
```


## Methods

- `protected virtual BindProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void BindProperties(Colossal.UI.Binding.IJsonWriter writer);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.UI.InGame.GamePanel+LayoutPosition`  

