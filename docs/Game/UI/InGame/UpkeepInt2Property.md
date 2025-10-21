# Game.UI.InGame.PrefabUISystem+UpkeepInt2Property

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct UpkeepInt2Property : Colossal.UI.Binding.IJsonWritable
{
    public System.String labelId;
    public Unity.Mathematics.int2 value;
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

- `public Unity.Mathematics.int2 value`  

```csharp
public Unity.Mathematics.int2 value;
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


