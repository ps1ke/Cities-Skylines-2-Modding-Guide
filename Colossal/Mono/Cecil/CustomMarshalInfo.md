# Colossal.Mono.Cecil.CustomMarshalInfo

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.MarshalInfo`  

## Code

```csharp
public sealed class CustomMarshalInfo : Colossal.Mono.Cecil.MarshalInfo
{
    internal System.Guid guid;
    internal System.String unmanaged_type;
    internal Colossal.Mono.Cecil.TypeReference managed_type;
    internal System.String cookie;

    public System.Guid Guid { get; set; }
    public System.String UnmanagedType { get; set; }
    public Colossal.Mono.Cecil.TypeReference ManagedType { get; set; }
    public System.String Cookie { get; set; }

    public CustomMarshalInfo();

}
```


## Fields

- `internal System.Guid guid`  

```csharp
internal System.Guid guid;
```

- `internal System.String unmanaged_type`  

```csharp
internal System.String unmanaged_type;
```

- `internal Colossal.Mono.Cecil.TypeReference managed_type`  

```csharp
internal Colossal.Mono.Cecil.TypeReference managed_type;
```

- `internal System.String cookie`  

```csharp
internal System.String cookie;
```


## Properties

- `public System.Guid Guid { get; set }`  

```csharp
public System.Guid Guid { get; set; }
```

- `public System.String UnmanagedType { get; set }`  

```csharp
public System.String UnmanagedType { get; set; }
```

- `public Colossal.Mono.Cecil.TypeReference ManagedType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference ManagedType { get; set; }
```

- `public System.String Cookie { get; set }`  

```csharp
public System.String Cookie { get; set; }
```


## Constructors

- `public CustomMarshalInfo()`  

```csharp
public CustomMarshalInfo();
```


