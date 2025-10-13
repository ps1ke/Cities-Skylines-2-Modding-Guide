# Game.UI.MapMetadataSystem+Connections

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct Connections : Colossal.UI.Binding.IJsonWritable
{
    public System.Boolean road;
    public System.Boolean train;
    public System.Boolean air;
    public System.Boolean ship;
    public System.Boolean electricity;
    public System.Boolean water;

    public Colossal.Json.ProxyObject ToVariant();
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.Boolean road`  

```csharp
public System.Boolean road;
```

- `public System.Boolean train`  

```csharp
public System.Boolean train;
```

- `public System.Boolean air`  

```csharp
public System.Boolean air;
```

- `public System.Boolean ship`  

```csharp
public System.Boolean ship;
```

- `public System.Boolean electricity`  

```csharp
public System.Boolean electricity;
```

- `public System.Boolean water`  

```csharp
public System.Boolean water;
```


## Methods

- `public ToVariant() : Colossal.Json.ProxyObject`  

```csharp
public Colossal.Json.ProxyObject ToVariant();
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


