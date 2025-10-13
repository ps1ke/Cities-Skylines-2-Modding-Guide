# Colossal.Mono.Cecil.SecurityDeclaration

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Code

```csharp
public sealed class SecurityDeclaration
{
    internal readonly System.UInt32 signature;
    private System.Byte[] blob;
    private readonly Colossal.Mono.Cecil.ModuleDefinition module;
    internal System.Boolean resolved;
    private Colossal.Mono.Cecil.SecurityAction action;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityAttribute> security_attributes;

    public Colossal.Mono.Cecil.SecurityAction Action { get; set; }
    public System.Boolean HasSecurityAttributes { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityAttribute> SecurityAttributes { get; }
    internal System.Boolean HasImage { internal get; }

    internal SecurityDeclaration(Colossal.Mono.Cecil.SecurityAction action, System.UInt32 signature, Colossal.Mono.Cecil.ModuleDefinition module);
    public SecurityDeclaration(Colossal.Mono.Cecil.SecurityAction action);
    public SecurityDeclaration(Colossal.Mono.Cecil.SecurityAction action, System.Byte[] blob);

    public System.Byte[] GetBlob();
    private System.Void Resolve();
}
```


## Fields

- `internal readonly System.UInt32 signature`  

```csharp
internal readonly System.UInt32 signature;
```

- `private System.Byte[] blob`  

```csharp
private System.Byte[] blob;
```

- `private readonly Colossal.Mono.Cecil.ModuleDefinition module`  

```csharp
private readonly Colossal.Mono.Cecil.ModuleDefinition module;
```

- `internal System.Boolean resolved`  

```csharp
internal System.Boolean resolved;
```

- `private Colossal.Mono.Cecil.SecurityAction action`  

```csharp
private Colossal.Mono.Cecil.SecurityAction action;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityAttribute> security_attributes`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityAttribute> security_attributes;
```


## Properties

- `public Colossal.Mono.Cecil.SecurityAction Action { get; set }`  

```csharp
public Colossal.Mono.Cecil.SecurityAction Action { get; set; }
```

- `public System.Boolean HasSecurityAttributes { get }`  

```csharp
public System.Boolean HasSecurityAttributes { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityAttribute> SecurityAttributes { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityAttribute> SecurityAttributes { get; }
```

- `internal System.Boolean HasImage { internal get }`  

```csharp
internal System.Boolean HasImage { internal get; }
```


## Constructors

- `internal SecurityDeclaration(Colossal.Mono.Cecil.SecurityAction action, System.UInt32 signature, Colossal.Mono.Cecil.ModuleDefinition module)`  

```csharp
internal SecurityDeclaration(Colossal.Mono.Cecil.SecurityAction action, System.UInt32 signature, Colossal.Mono.Cecil.ModuleDefinition module);
```

- `public SecurityDeclaration(Colossal.Mono.Cecil.SecurityAction action)`  

```csharp
public SecurityDeclaration(Colossal.Mono.Cecil.SecurityAction action);
```

- `public SecurityDeclaration(Colossal.Mono.Cecil.SecurityAction action, System.Byte[] blob)`  

```csharp
public SecurityDeclaration(Colossal.Mono.Cecil.SecurityAction action, System.Byte[] blob);
```


## Methods

- `public GetBlob() : System.Byte[]`  

```csharp
public System.Byte[] GetBlob();
```

- `private Resolve() : System.Void`  

```csharp
private System.Void Resolve();
```


## Nested types

- `Colossal.Mono.Cecil.SecurityDeclaration+<>c`  

