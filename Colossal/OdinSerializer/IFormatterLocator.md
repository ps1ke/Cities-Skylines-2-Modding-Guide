# Colossal.OdinSerializer.IFormatterLocator

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IFormatterLocator
{
    public abstract System.Boolean TryGetFormatter(System.Type type, Colossal.OdinSerializer.FormatterLocationStep step, Colossal.OdinSerializer.ISerializationPolicy policy, System.Boolean allowWeakFallbackFormatters, Colossal.OdinSerializer.IFormatter& formatter);
}
```


## Methods

- `public abstract TryGetFormatter(System.Type type, Colossal.OdinSerializer.FormatterLocationStep step, Colossal.OdinSerializer.ISerializationPolicy policy, System.Boolean allowWeakFallbackFormatters, Colossal.OdinSerializer.IFormatter& formatter) : System.Boolean`  

```csharp
public abstract System.Boolean TryGetFormatter(System.Type type, Colossal.OdinSerializer.FormatterLocationStep step, Colossal.OdinSerializer.ISerializationPolicy policy, System.Boolean allowWeakFallbackFormatters, Colossal.OdinSerializer.IFormatter& formatter);
```


