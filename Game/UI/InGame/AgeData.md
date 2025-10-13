# Game.UI.InGame.AgeData

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct AgeData : Colossal.UI.Binding.IJsonWritable
{
    private readonly System.Int32 <children>k__BackingField;
    private readonly System.Int32 <teens>k__BackingField;
    private readonly System.Int32 <adults>k__BackingField;
    private readonly System.Int32 <elders>k__BackingField;

    public System.Int32 children { get; }
    public System.Int32 teens { get; }
    public System.Int32 adults { get; }
    public System.Int32 elders { get; }

    public AgeData(System.Int32 children, System.Int32 teens, System.Int32 adults, System.Int32 elders);

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly System.Int32 <children>k__BackingField`  

```csharp
private readonly System.Int32 <children>k__BackingField;
```

- `private readonly System.Int32 <teens>k__BackingField`  

```csharp
private readonly System.Int32 <teens>k__BackingField;
```

- `private readonly System.Int32 <adults>k__BackingField`  

```csharp
private readonly System.Int32 <adults>k__BackingField;
```

- `private readonly System.Int32 <elders>k__BackingField`  

```csharp
private readonly System.Int32 <elders>k__BackingField;
```


## Properties

- `public System.Int32 children { get }`  

```csharp
public System.Int32 children { get; }
```

- `public System.Int32 teens { get }`  

```csharp
public System.Int32 teens { get; }
```

- `public System.Int32 adults { get }`  

```csharp
public System.Int32 adults { get; }
```

- `public System.Int32 elders { get }`  

```csharp
public System.Int32 elders { get; }
```


## Constructors

- `public AgeData(System.Int32 children, System.Int32 teens, System.Int32 adults, System.Int32 elders)`  

```csharp
public AgeData(System.Int32 children, System.Int32 teens, System.Int32 adults, System.Int32 elders);
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


