# Colossal.Mono.Cecil.EventReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class abstract public  

**Base:** `Colossal.Mono.Cecil.MemberReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public abstract class EventReference : Colossal.Mono.Cecil.MemberReference, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    private Colossal.Mono.Cecil.TypeReference event_type;

    public Colossal.Mono.Cecil.TypeReference EventType { get; set; }
    public System.String FullName { get; }

    protected EventReference(System.String name, Colossal.Mono.Cecil.TypeReference eventType);

    public abstract Colossal.Mono.Cecil.EventDefinition Resolve();
    protected virtual Colossal.Mono.Cecil.IMemberDefinition ResolveDefinition();
}
```


## Fields

- `private Colossal.Mono.Cecil.TypeReference event_type`  

```csharp
private Colossal.Mono.Cecil.TypeReference event_type;
```


## Properties

- `public Colossal.Mono.Cecil.TypeReference EventType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference EventType { get; set; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```


## Constructors

- `protected EventReference(System.String name, Colossal.Mono.Cecil.TypeReference eventType)`  

```csharp
protected EventReference(System.String name, Colossal.Mono.Cecil.TypeReference eventType);
```


## Methods

- `public abstract Resolve() : Colossal.Mono.Cecil.EventDefinition`  

```csharp
public abstract Colossal.Mono.Cecil.EventDefinition Resolve();
```

- `protected virtual ResolveDefinition() : Colossal.Mono.Cecil.IMemberDefinition`  

```csharp
protected virtual Colossal.Mono.Cecil.IMemberDefinition ResolveDefinition();
```


