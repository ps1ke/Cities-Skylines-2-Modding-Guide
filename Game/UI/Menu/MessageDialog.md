# Game.UI.Menu.ParadoxBindings+MessageDialog

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class abstract public  

**Base:** `Game.UI.Menu.ParadoxBindings+ParadoxDialog`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public abstract class MessageDialog : Game.UI.Menu.ParadoxBindings+ParadoxDialog, Colossal.UI.Binding.IJsonWritable
{
    public readonly System.String icon;
    public readonly System.String titleId;
    public readonly System.String messageId;
    public readonly System.Collections.Generic.Dictionary<System.String, System.String> messageArgs;

    protected MessageDialog(System.String icon, System.String titleId, System.String messageId, System.Collections.Generic.Dictionary<System.String, System.String> messageArgs);

    public virtual System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public readonly System.String icon`  

```csharp
public readonly System.String icon;
```

- `public readonly System.String titleId`  

```csharp
public readonly System.String titleId;
```

- `public readonly System.String messageId`  

```csharp
public readonly System.String messageId;
```

- `public readonly System.Collections.Generic.Dictionary<System.String, System.String> messageArgs`  

```csharp
public readonly System.Collections.Generic.Dictionary<System.String, System.String> messageArgs;
```


## Constructors

- `protected MessageDialog(System.String icon, System.String titleId, System.String messageId, System.Collections.Generic.Dictionary<System.String, System.String> messageArgs)`  

```csharp
protected MessageDialog(System.String icon, System.String titleId, System.String messageId, System.Collections.Generic.Dictionary<System.String, System.String> messageArgs);
```


## Methods

- `public virtual Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public virtual System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


