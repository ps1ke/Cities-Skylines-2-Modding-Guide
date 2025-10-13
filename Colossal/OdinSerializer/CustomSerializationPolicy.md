# Colossal.OdinSerializer.CustomSerializationPolicy

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.ISerializationPolicy`  

## Code

```csharp
public class CustomSerializationPolicy : Colossal.OdinSerializer.ISerializationPolicy
{
    private System.String id;
    private System.Boolean allowNonSerializableTypes;
    private System.Func<System.Reflection.MemberInfo, System.Boolean> shouldSerializeFunc;

    public System.String ID { get; }
    public System.Boolean AllowNonSerializableTypes { get; }

    public CustomSerializationPolicy(System.String id, System.Boolean allowNonSerializableTypes, System.Func<System.Reflection.MemberInfo, System.Boolean> shouldSerializeFunc);

    public System.Boolean ShouldSerializeMember(System.Reflection.MemberInfo member);
}
```


## Fields

- `private System.String id`  

```csharp
private System.String id;
```

- `private System.Boolean allowNonSerializableTypes`  

```csharp
private System.Boolean allowNonSerializableTypes;
```

- `private System.Func<System.Reflection.MemberInfo, System.Boolean> shouldSerializeFunc`  

```csharp
private System.Func<System.Reflection.MemberInfo, System.Boolean> shouldSerializeFunc;
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


## Constructors

- `public CustomSerializationPolicy(System.String id, System.Boolean allowNonSerializableTypes, System.Func<System.Reflection.MemberInfo, System.Boolean> shouldSerializeFunc)`  

```csharp
public CustomSerializationPolicy(System.String id, System.Boolean allowNonSerializableTypes, System.Func<System.Reflection.MemberInfo, System.Boolean> shouldSerializeFunc);
```


## Methods

- `public ShouldSerializeMember(System.Reflection.MemberInfo member) : System.Boolean`  

```csharp
public System.Boolean ShouldSerializeMember(System.Reflection.MemberInfo member);
```


