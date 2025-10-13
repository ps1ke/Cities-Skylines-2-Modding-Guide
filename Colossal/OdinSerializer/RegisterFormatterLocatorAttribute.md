# Colossal.OdinSerializer.RegisterFormatterLocatorAttribute

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class RegisterFormatterLocatorAttribute : System.Attribute
{
    private System.Type <FormatterLocatorType>k__BackingField;
    private System.Int32 <Priority>k__BackingField;

    public System.Type FormatterLocatorType { get; private set; }
    public System.Int32 Priority { get; private set; }

    public RegisterFormatterLocatorAttribute(System.Type formatterLocatorType, System.Int32 priority);

}
```


## Fields

- `private System.Type <FormatterLocatorType>k__BackingField`  

```csharp
private System.Type <FormatterLocatorType>k__BackingField;
```

- `private System.Int32 <Priority>k__BackingField`  

```csharp
private System.Int32 <Priority>k__BackingField;
```


## Properties

- `public System.Type FormatterLocatorType { get; private set }`  

```csharp
public System.Type FormatterLocatorType { get; private set; }
```

- `public System.Int32 Priority { get; private set }`  

```csharp
public System.Int32 Priority { get; private set; }
```


## Constructors

- `public RegisterFormatterLocatorAttribute(System.Type formatterLocatorType, System.Int32 priority = 0)`  

```csharp
public RegisterFormatterLocatorAttribute(System.Type formatterLocatorType, System.Int32 priority);
```


