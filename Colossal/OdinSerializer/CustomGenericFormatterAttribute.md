# Colossal.OdinSerializer.CustomGenericFormatterAttribute

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.CustomFormatterAttribute`  

**Attributes:** `Usage`, `Obsolete`, `EditorBrowsable`  

## Code

```csharp
public class CustomGenericFormatterAttribute : Colossal.OdinSerializer.CustomFormatterAttribute
{
    public readonly System.Type SerializedGenericTypeDefinition;

    public CustomGenericFormatterAttribute(System.Type serializedGenericTypeDefinition, System.Int32 priority);

}
```


## Fields

- `public readonly System.Type SerializedGenericTypeDefinition`  

```csharp
public readonly System.Type SerializedGenericTypeDefinition;
```


## Constructors

- `public CustomGenericFormatterAttribute(System.Type serializedGenericTypeDefinition, System.Int32 priority = 0)`  

```csharp
public CustomGenericFormatterAttribute(System.Type serializedGenericTypeDefinition, System.Int32 priority);
```


