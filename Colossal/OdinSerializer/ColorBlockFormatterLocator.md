# Colossal.OdinSerializer.ColorBlockFormatterLocator

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.IFormatterLocator`  

## Code

```csharp
public class ColorBlockFormatterLocator : Colossal.OdinSerializer.IFormatterLocator
{
    public ColorBlockFormatterLocator();

    public System.Boolean TryGetFormatter(System.Type type, Colossal.OdinSerializer.FormatterLocationStep step, Colossal.OdinSerializer.ISerializationPolicy policy, System.Boolean allowWeakFallbackFormatters, Colossal.OdinSerializer.IFormatter& formatter);
}
```


## Constructors

- `public ColorBlockFormatterLocator()`  

```csharp
public ColorBlockFormatterLocator();
```


## Methods

- `public TryGetFormatter(System.Type type, Colossal.OdinSerializer.FormatterLocationStep step, Colossal.OdinSerializer.ISerializationPolicy policy, System.Boolean allowWeakFallbackFormatters, Colossal.OdinSerializer.IFormatter& formatter) : System.Boolean`  

```csharp
public System.Boolean TryGetFormatter(System.Type type, Colossal.OdinSerializer.FormatterLocationStep step, Colossal.OdinSerializer.ISerializationPolicy policy, System.Boolean allowWeakFallbackFormatters, Colossal.OdinSerializer.IFormatter& formatter);
```


