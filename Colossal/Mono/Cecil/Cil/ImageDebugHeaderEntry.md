# Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Code

```csharp
public sealed class ImageDebugHeaderEntry
{
    private Colossal.Mono.Cecil.Cil.ImageDebugDirectory directory;
    private readonly System.Byte[] data;

    public Colossal.Mono.Cecil.Cil.ImageDebugDirectory Directory { get; internal set; }
    public System.Byte[] Data { get; }

    public ImageDebugHeaderEntry(Colossal.Mono.Cecil.Cil.ImageDebugDirectory directory, System.Byte[] data);

}
```


## Fields

- `private Colossal.Mono.Cecil.Cil.ImageDebugDirectory directory`  

```csharp
private Colossal.Mono.Cecil.Cil.ImageDebugDirectory directory;
```

- `private readonly System.Byte[] data`  

```csharp
private readonly System.Byte[] data;
```


## Properties

- `public Colossal.Mono.Cecil.Cil.ImageDebugDirectory Directory { get; internal set }`  

```csharp
public Colossal.Mono.Cecil.Cil.ImageDebugDirectory Directory { get; internal set; }
```

- `public System.Byte[] Data { get }`  

```csharp
public System.Byte[] Data { get; }
```


## Constructors

- `public ImageDebugHeaderEntry(Colossal.Mono.Cecil.Cil.ImageDebugDirectory directory, System.Byte[] data)`  

```csharp
public ImageDebugHeaderEntry(Colossal.Mono.Cecil.Cil.ImageDebugDirectory directory, System.Byte[] data);
```


