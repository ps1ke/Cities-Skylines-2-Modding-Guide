# Game.UI.InGame.StatisticsUISystem+DataPoint

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct DataPoint : Colossal.UI.Binding.IJsonWritable
{
    public System.Int64 x;
    public System.Int64 y;

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.Int64 x`  

```csharp
public System.Int64 x;
```

- `public System.Int64 y`  

```csharp
public System.Int64 y;
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


