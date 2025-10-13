# Game.UI.Menu.ParadoxBindings+MultiOptionDialog

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.Menu.ParadoxBindings+ParadoxDialog`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class MultiOptionDialog : Game.UI.Menu.ParadoxBindings+ParadoxDialog, Colossal.UI.Binding.IJsonWritable
{
    public System.String m_TitleId;
    public System.String m_MessageId;
    public Game.UI.Menu.ParadoxBindings+MultiOptionDialog+Option[] m_Options;

    public MultiOptionDialog(System.String titleId, System.String messageId, Game.UI.Menu.ParadoxBindings+MultiOptionDialog+Option[] options);

    public virtual System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.String m_TitleId`  

```csharp
public System.String m_TitleId;
```

- `public System.String m_MessageId`  

```csharp
public System.String m_MessageId;
```

- `public Game.UI.Menu.ParadoxBindings+MultiOptionDialog+Option[] m_Options`  

```csharp
public Game.UI.Menu.ParadoxBindings+MultiOptionDialog+Option[] m_Options;
```


## Constructors

- `public MultiOptionDialog(System.String titleId, System.String messageId, Game.UI.Menu.ParadoxBindings+MultiOptionDialog+Option[] options)`  

```csharp
public MultiOptionDialog(System.String titleId, System.String messageId, Game.UI.Menu.ParadoxBindings+MultiOptionDialog+Option[] options);
```


## Methods

- `public virtual Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public virtual System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.UI.Menu.ParadoxBindings+MultiOptionDialog+Option`  

