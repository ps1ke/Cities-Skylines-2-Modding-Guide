# Game.UI.InGame.EducationData

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct EducationData : Colossal.UI.Binding.IJsonWritable
{
    private readonly System.Int32 <uneducated>k__BackingField;
    private readonly System.Int32 <poorlyEducated>k__BackingField;
    private readonly System.Int32 <educated>k__BackingField;
    private readonly System.Int32 <wellEducated>k__BackingField;
    private readonly System.Int32 <highlyEducated>k__BackingField;
    private readonly System.Int32 <total>k__BackingField;

    public System.Int32 uneducated { get; }
    public System.Int32 poorlyEducated { get; }
    public System.Int32 educated { get; }
    public System.Int32 wellEducated { get; }
    public System.Int32 highlyEducated { get; }
    public System.Int32 total { get; }

    public EducationData(System.Int32 uneducated, System.Int32 poorlyEducated, System.Int32 educated, System.Int32 wellEducated, System.Int32 highlyEducated);

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly System.Int32 <uneducated>k__BackingField`  

```csharp
private readonly System.Int32 <uneducated>k__BackingField;
```

- `private readonly System.Int32 <poorlyEducated>k__BackingField`  

```csharp
private readonly System.Int32 <poorlyEducated>k__BackingField;
```

- `private readonly System.Int32 <educated>k__BackingField`  

```csharp
private readonly System.Int32 <educated>k__BackingField;
```

- `private readonly System.Int32 <wellEducated>k__BackingField`  

```csharp
private readonly System.Int32 <wellEducated>k__BackingField;
```

- `private readonly System.Int32 <highlyEducated>k__BackingField`  

```csharp
private readonly System.Int32 <highlyEducated>k__BackingField;
```

- `private readonly System.Int32 <total>k__BackingField`  

```csharp
private readonly System.Int32 <total>k__BackingField;
```


## Properties

- `public System.Int32 uneducated { get }`  

```csharp
public System.Int32 uneducated { get; }
```

- `public System.Int32 poorlyEducated { get }`  

```csharp
public System.Int32 poorlyEducated { get; }
```

- `public System.Int32 educated { get }`  

```csharp
public System.Int32 educated { get; }
```

- `public System.Int32 wellEducated { get }`  

```csharp
public System.Int32 wellEducated { get; }
```

- `public System.Int32 highlyEducated { get }`  

```csharp
public System.Int32 highlyEducated { get; }
```

- `public System.Int32 total { get }`  

```csharp
public System.Int32 total { get; }
```


## Constructors

- `public EducationData(System.Int32 uneducated, System.Int32 poorlyEducated, System.Int32 educated, System.Int32 wellEducated, System.Int32 highlyEducated)`  

```csharp
public EducationData(System.Int32 uneducated, System.Int32 poorlyEducated, System.Int32 educated, System.Int32 wellEducated, System.Int32 highlyEducated);
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


