# Colossal.OdinSerializer.WeakColorBlockFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.WeakBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class WeakColorBlockFormatter : Colossal.OdinSerializer.WeakBaseFormatter, Colossal.OdinSerializer.IFormatter
{
    private readonly System.Reflection.PropertyInfo normalColor;
    private readonly System.Reflection.PropertyInfo highlightedColor;
    private readonly System.Reflection.PropertyInfo pressedColor;
    private readonly System.Reflection.PropertyInfo disabledColor;
    private readonly System.Reflection.PropertyInfo colorMultiplier;
    private readonly System.Reflection.PropertyInfo fadeDuration;
    private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;
    private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.Color> ColorSerializer;

    public WeakColorBlockFormatter(System.Type colorBlockType);

    protected virtual System.Void DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private readonly System.Reflection.PropertyInfo normalColor`  

```csharp
private readonly System.Reflection.PropertyInfo normalColor;
```

- `private readonly System.Reflection.PropertyInfo highlightedColor`  

```csharp
private readonly System.Reflection.PropertyInfo highlightedColor;
```

- `private readonly System.Reflection.PropertyInfo pressedColor`  

```csharp
private readonly System.Reflection.PropertyInfo pressedColor;
```

- `private readonly System.Reflection.PropertyInfo disabledColor`  

```csharp
private readonly System.Reflection.PropertyInfo disabledColor;
```

- `private readonly System.Reflection.PropertyInfo colorMultiplier`  

```csharp
private readonly System.Reflection.PropertyInfo colorMultiplier;
```

- `private readonly System.Reflection.PropertyInfo fadeDuration`  

```csharp
private readonly System.Reflection.PropertyInfo fadeDuration;
```

- `private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Single> FloatSerializer;
```

- `private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.Color> ColorSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<UnityEngine.Color> ColorSerializer;
```


## Constructors

- `public WeakColorBlockFormatter(System.Type colorBlockType)`  

```csharp
public WeakColorBlockFormatter(System.Type colorBlockType);
```


## Methods

- `protected virtual DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
```


