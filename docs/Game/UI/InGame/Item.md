# Game.UI.InGame.InfoList+Item

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct Item : Colossal.UI.Binding.IJsonWritable
{
    private readonly System.String <text>k__BackingField;
    private readonly Unity.Entities.Entity <entity>k__BackingField;
    public static readonly Unity.Entities.Entity kNullEntity;

    public System.String text { get; }
    public Unity.Entities.Entity entity { get; }

    public Item(System.String text, Unity.Entities.Entity entity);
    public Item(System.String text);

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly System.String <text>k__BackingField`  

```csharp
private readonly System.String <text>k__BackingField;
```

- `private readonly Unity.Entities.Entity <entity>k__BackingField`  

```csharp
private readonly Unity.Entities.Entity <entity>k__BackingField;
```

- `public static readonly Unity.Entities.Entity kNullEntity`  

```csharp
public static readonly Unity.Entities.Entity kNullEntity;
```


## Properties

- `public System.String text { get }`  

```csharp
public System.String text { get; }
```

- `public Unity.Entities.Entity entity { get }`  

```csharp
public Unity.Entities.Entity entity { get; }
```


## Constructors

- `public Item(System.String text, Unity.Entities.Entity entity)`  

```csharp
public Item(System.String text, Unity.Entities.Entity entity);
```

- `public Item(System.String text)`  

```csharp
public Item(System.String text);
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


