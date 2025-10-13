# Game.UI.Menu.ParadoxBindings+MultiOptionDialog+Option

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct Option : Colossal.UI.Binding.IJsonWritable
{
    public System.String m_Id;
    public System.Action m_OnSelect;

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.String m_Id`  

```csharp
public System.String m_Id;
```

- `public System.Action m_OnSelect`  

```csharp
public System.Action m_OnSelect;
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


