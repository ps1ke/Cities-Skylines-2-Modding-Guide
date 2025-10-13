# Game.UI.InGame.StringProperty

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct StringProperty : Colossal.UI.Binding.IJsonWritable
{
    public System.String labelId;
    public System.String valueId;
    public System.String icon;
    public System.String valueIcon;

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.String labelId`  

```csharp
public System.String labelId;
```

- `public System.String valueId`  

```csharp
public System.String valueId;
```

- `public System.String icon`  

```csharp
public System.String icon;
```

- `public System.String valueIcon`  

```csharp
public System.String valueIcon;
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


