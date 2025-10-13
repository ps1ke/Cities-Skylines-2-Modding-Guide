# Game.UI.Menu.ParadoxBindings+ErrorDialog

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.Menu.ParadoxBindings+ParadoxDialog`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class ErrorDialog : Game.UI.Menu.ParadoxBindings+ParadoxDialog, Colossal.UI.Binding.IJsonWritable
{
    public readonly System.String messageId;
    public readonly System.String message;

    public ErrorDialog(System.String messageId, System.String message);

    public virtual System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public readonly System.String messageId`  

```csharp
public readonly System.String messageId;
```

- `public readonly System.String message`  

```csharp
public readonly System.String message;
```


## Constructors

- `public ErrorDialog(System.String messageId, System.String message)`  

```csharp
public ErrorDialog(System.String messageId, System.String message);
```


## Methods

- `public virtual Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public virtual System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


