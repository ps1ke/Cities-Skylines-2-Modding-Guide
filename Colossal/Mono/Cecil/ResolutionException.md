# Colossal.Mono.Cecil.ResolutionException

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Exception`  
**Implements:** `System.Runtime.Serialization.ISerializable`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed class ResolutionException : System.Exception, System.Runtime.Serialization.ISerializable
{
    private readonly Colossal.Mono.Cecil.MemberReference member;

    public Colossal.Mono.Cecil.MemberReference Member { get; }
    public Colossal.Mono.Cecil.IMetadataScope Scope { get; }

    public ResolutionException(Colossal.Mono.Cecil.MemberReference member);
    public ResolutionException(Colossal.Mono.Cecil.MemberReference member, System.Exception innerException);
    private ResolutionException(System.Runtime.Serialization.SerializationInfo info, System.Runtime.Serialization.StreamingContext context);

}
```


## Fields

- `private readonly Colossal.Mono.Cecil.MemberReference member`  

```csharp
private readonly Colossal.Mono.Cecil.MemberReference member;
```


## Properties

- `public Colossal.Mono.Cecil.MemberReference Member { get }`  

```csharp
public Colossal.Mono.Cecil.MemberReference Member { get; }
```

- `public Colossal.Mono.Cecil.IMetadataScope Scope { get }`  

```csharp
public Colossal.Mono.Cecil.IMetadataScope Scope { get; }
```


## Constructors

- `public ResolutionException(Colossal.Mono.Cecil.MemberReference member)`  

```csharp
public ResolutionException(Colossal.Mono.Cecil.MemberReference member);
```

- `public ResolutionException(Colossal.Mono.Cecil.MemberReference member, System.Exception innerException)`  

```csharp
public ResolutionException(Colossal.Mono.Cecil.MemberReference member, System.Exception innerException);
```

- `private ResolutionException(System.Runtime.Serialization.SerializationInfo info, System.Runtime.Serialization.StreamingContext context)`  

```csharp
private ResolutionException(System.Runtime.Serialization.SerializationInfo info, System.Runtime.Serialization.StreamingContext context);
```


