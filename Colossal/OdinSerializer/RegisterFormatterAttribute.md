# Colossal.OdinSerializer.RegisterFormatterAttribute

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class RegisterFormatterAttribute : System.Attribute
{
    private System.Type <FormatterType>k__BackingField;
    private System.Type <WeakFallback>k__BackingField;
    private System.Int32 <Priority>k__BackingField;

    public System.Type FormatterType { get; private set; }
    public System.Type WeakFallback { get; private set; }
    public System.Int32 Priority { get; private set; }

    public RegisterFormatterAttribute(System.Type formatterType, System.Int32 priority);
    public RegisterFormatterAttribute(System.Type formatterType, System.Type weakFallback, System.Int32 priority);

}
```


## Fields

- `private System.Type <FormatterType>k__BackingField`  

```csharp
private System.Type <FormatterType>k__BackingField;
```

- `private System.Type <WeakFallback>k__BackingField`  

```csharp
private System.Type <WeakFallback>k__BackingField;
```

- `private System.Int32 <Priority>k__BackingField`  

```csharp
private System.Int32 <Priority>k__BackingField;
```


## Properties

- `public System.Type FormatterType { get; private set }`  

```csharp
public System.Type FormatterType { get; private set; }
```

- `public System.Type WeakFallback { get; private set }`  

```csharp
public System.Type WeakFallback { get; private set; }
```

- `public System.Int32 Priority { get; private set }`  

```csharp
public System.Int32 Priority { get; private set; }
```


## Constructors

- `public RegisterFormatterAttribute(System.Type formatterType, System.Int32 priority = 0)`  

```csharp
public RegisterFormatterAttribute(System.Type formatterType, System.Int32 priority);
```

- `public RegisterFormatterAttribute(System.Type formatterType, System.Type weakFallback, System.Int32 priority = 0)`  

```csharp
public RegisterFormatterAttribute(System.Type formatterType, System.Type weakFallback, System.Int32 priority);
```


