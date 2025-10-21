# Game.UI.InGame.PrefabUISystem+UpkeepIntProperty

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct UpkeepIntProperty : Colossal.UI.Binding.IJsonWritable
{
    public System.String labelId;
    public System.Int32 value;
    public System.String unit;
    public System.Boolean signed;

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.String labelId`  

```csharp
public System.String labelId;
```

- `public System.Int32 value`  

```csharp
public System.Int32 value;
```

- `public System.String unit`  

```csharp
public System.String unit;
```

- `public System.Boolean signed`  

```csharp
public System.Boolean signed;
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


