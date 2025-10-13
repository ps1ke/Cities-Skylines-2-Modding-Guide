# Game.UI.MapMetadataSystem+Resources

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct Resources : Colossal.UI.Binding.IJsonWritable
{
    public System.Single fertile;
    public System.Single forest;
    public System.Single oil;
    public System.Single ore;
    public System.Single fish;

    public Colossal.Json.ProxyObject ToVariant();
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.Single fertile`  

```csharp
public System.Single fertile;
```

- `public System.Single forest`  

```csharp
public System.Single forest;
```

- `public System.Single oil`  

```csharp
public System.Single oil;
```

- `public System.Single ore`  

```csharp
public System.Single ore;
```

- `public System.Single fish`  

```csharp
public System.Single fish;
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


