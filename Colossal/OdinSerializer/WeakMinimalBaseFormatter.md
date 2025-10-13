# Colossal.OdinSerializer.WeakMinimalBaseFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public abstract class WeakMinimalBaseFormatter : Colossal.OdinSerializer.IFormatter
{
    protected readonly System.Type SerializedType;
    protected readonly System.Boolean IsValueType;

    private System.Type Colossal.OdinSerializer.IFormatter.SerializedType { private get; }

    public WeakMinimalBaseFormatter(System.Type serializedType);

    public System.Object Deserialize(Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Object GetUninitializedObject();
    protected abstract System.Void Read(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
    protected System.Void RegisterReferenceID(System.Object value, Colossal.OdinSerializer.IDataReader reader);
    public System.Void Serialize(System.Object value, Colossal.OdinSerializer.IDataWriter writer);
    protected abstract System.Void Write(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `protected readonly System.Type SerializedType`  

```csharp
protected readonly System.Type SerializedType;
```

- `protected readonly System.Boolean IsValueType`  

```csharp
protected readonly System.Boolean IsValueType;
```


## Properties

- `private System.Type Colossal.OdinSerializer.IFormatter.SerializedType { private get }`  

```csharp
private System.Type Colossal.OdinSerializer.IFormatter.SerializedType { private get; }
```


## Constructors

- `public WeakMinimalBaseFormatter(System.Type serializedType)`  

```csharp
public WeakMinimalBaseFormatter(System.Type serializedType);
```


## Methods

- `public Deserialize(Colossal.OdinSerializer.IDataReader reader) : System.Object`  

```csharp
public System.Object Deserialize(Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual GetUninitializedObject() : System.Object`  

```csharp
protected virtual System.Object GetUninitializedObject();
```

- `protected abstract Read(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected abstract System.Void Read(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected RegisterReferenceID(System.Object value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected System.Void RegisterReferenceID(System.Object value, Colossal.OdinSerializer.IDataReader reader);
```

- `public Serialize(System.Object value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public System.Void Serialize(System.Object value, Colossal.OdinSerializer.IDataWriter writer);
```

- `protected abstract Write(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected abstract System.Void Write(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
```


