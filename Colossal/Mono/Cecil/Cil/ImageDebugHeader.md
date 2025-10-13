# Colossal.Mono.Cecil.Cil.ImageDebugHeader

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Code

```csharp
public sealed class ImageDebugHeader
{
    private readonly Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry[] entries;

    public System.Boolean HasEntries { get; }
    public Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry[] Entries { get; }

    public ImageDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry[] entries);
    public ImageDebugHeader();
    public ImageDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry entry);

}
```


## Fields

- `private readonly Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry[] entries`  

```csharp
private readonly Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry[] entries;
```


## Properties

- `public System.Boolean HasEntries { get }`  

```csharp
public System.Boolean HasEntries { get; }
```

- `public Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry[] Entries { get }`  

```csharp
public Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry[] Entries { get; }
```


## Constructors

- `public ImageDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry[] entries)`  

```csharp
public ImageDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry[] entries);
```

- `public ImageDebugHeader()`  

```csharp
public ImageDebugHeader();
```

- `public ImageDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry entry)`  

```csharp
public ImageDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry entry);
```


