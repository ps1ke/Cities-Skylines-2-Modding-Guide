# Game.UI.InGame.MapTilesUISystem+UIMapTileResource

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct UIMapTileResource : Colossal.UI.Binding.IJsonWritable
{
    private readonly System.String <id>k__BackingField;
    private readonly System.String <icon>k__BackingField;
    private readonly System.Single <value>k__BackingField;
    private readonly System.String <unit>k__BackingField;

    public System.String id { get; }
    public System.String icon { get; }
    public System.Single value { get; }
    public System.String unit { get; }

    public UIMapTileResource(System.String id, System.String icon, System.Single value, System.String unit);

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly System.String <id>k__BackingField`  

```csharp
private readonly System.String <id>k__BackingField;
```

- `private readonly System.String <icon>k__BackingField`  

```csharp
private readonly System.String <icon>k__BackingField;
```

- `private readonly System.Single <value>k__BackingField`  

```csharp
private readonly System.Single <value>k__BackingField;
```

- `private readonly System.String <unit>k__BackingField`  

```csharp
private readonly System.String <unit>k__BackingField;
```


## Properties

- `public System.String id { get }`  

```csharp
public System.String id { get; }
```

- `public System.String icon { get }`  

```csharp
public System.String icon { get; }
```

- `public System.Single value { get }`  

```csharp
public System.Single value { get; }
```

- `public System.String unit { get }`  

```csharp
public System.String unit { get; }
```


## Constructors

- `public UIMapTileResource(System.String id, System.String icon, System.Single value, System.String unit)`  

```csharp
public UIMapTileResource(System.String id, System.String icon, System.Single value, System.String unit);
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


