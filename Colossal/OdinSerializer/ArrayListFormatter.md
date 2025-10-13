# Colossal.OdinSerializer.ArrayListFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.BaseFormatter<System.Collections.ArrayList>`  
**Implements:** `Colossal.OdinSerializer.IFormatter<System.Collections.ArrayList>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class ArrayListFormatter : Colossal.OdinSerializer.BaseFormatter<System.Collections.ArrayList>, Colossal.OdinSerializer.IFormatter<System.Collections.ArrayList>, Colossal.OdinSerializer.IFormatter
{
    private static readonly Colossal.OdinSerializer.Serializer<System.Object> ObjectSerializer;

    public ArrayListFormatter();

    protected virtual System.Void DeserializeImplementation(System.Collections.ArrayList& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Collections.ArrayList GetUninitializedObject();
    protected virtual System.Void SerializeImplementation(System.Collections.ArrayList& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Serializer<System.Object> ObjectSerializer`  

```csharp
private static readonly Colossal.OdinSerializer.Serializer<System.Object> ObjectSerializer;
```


## Constructors

- `public ArrayListFormatter()`  

```csharp
public ArrayListFormatter();
```


## Methods

- `protected virtual DeserializeImplementation(System.Collections.ArrayList& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void DeserializeImplementation(System.Collections.ArrayList& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual GetUninitializedObject() : System.Collections.ArrayList`  

```csharp
protected virtual System.Collections.ArrayList GetUninitializedObject();
```

- `protected virtual SerializeImplementation(System.Collections.ArrayList& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void SerializeImplementation(System.Collections.ArrayList& value, Colossal.OdinSerializer.IDataWriter writer);
```


