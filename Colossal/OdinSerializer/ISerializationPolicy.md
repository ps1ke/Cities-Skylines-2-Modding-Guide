# Colossal.OdinSerializer.ISerializationPolicy

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ISerializationPolicy
{
    public System.String ID { get; }
    public System.Boolean AllowNonSerializableTypes { get; }

    public abstract System.Boolean ShouldSerializeMember(System.Reflection.MemberInfo member);
}
```


## Properties

- `public System.String ID { get }`  

```csharp
public System.String ID { get; }
```

- `public System.Boolean AllowNonSerializableTypes { get }`  

```csharp
public System.Boolean AllowNonSerializableTypes { get; }
```


## Methods

- `public abstract ShouldSerializeMember(System.Reflection.MemberInfo member) : System.Boolean`  

```csharp
public abstract System.Boolean ShouldSerializeMember(System.Reflection.MemberInfo member);
```


