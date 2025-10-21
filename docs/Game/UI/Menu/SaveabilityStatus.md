# Game.UI.Menu.MenuUISystem+SaveabilityStatus

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct SaveabilityStatus : Colossal.UI.Binding.IJsonWritable
{
    public System.Boolean canSave;
    public System.String reasonHash;

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.Boolean canSave`  

```csharp
public System.Boolean canSave;
```

- `public System.String reasonHash`  

```csharp
public System.String reasonHash;
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


