# Colossal.Mono.Cecil.Cil.Document

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Cil.DebugInformation`  
**Implements:** `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public sealed class Document : Colossal.Mono.Cecil.Cil.DebugInformation, Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    private System.String url;
    private System.Guid type;
    private System.Guid hash_algorithm;
    private System.Guid language;
    private System.Guid language_vendor;
    private System.Byte[] hash;
    private System.Byte[] embedded_source;

    public System.String Url { get; set; }
    public Colossal.Mono.Cecil.Cil.DocumentType Type { get; set; }
    public System.Guid TypeGuid { get; set; }
    public Colossal.Mono.Cecil.Cil.DocumentHashAlgorithm HashAlgorithm { get; set; }
    public System.Guid HashAlgorithmGuid { get; set; }
    public Colossal.Mono.Cecil.Cil.DocumentLanguage Language { get; set; }
    public System.Guid LanguageGuid { get; set; }
    public Colossal.Mono.Cecil.Cil.DocumentLanguageVendor LanguageVendor { get; set; }
    public System.Guid LanguageVendorGuid { get; set; }
    public System.Byte[] Hash { get; set; }
    public System.Byte[] EmbeddedSource { get; set; }

    public Document(System.String url);

}
```


## Fields

- `private System.String url`  

```csharp
private System.String url;
```

- `private System.Guid type`  

```csharp
private System.Guid type;
```

- `private System.Guid hash_algorithm`  

```csharp
private System.Guid hash_algorithm;
```

- `private System.Guid language`  

```csharp
private System.Guid language;
```

- `private System.Guid language_vendor`  

```csharp
private System.Guid language_vendor;
```

- `private System.Byte[] hash`  

```csharp
private System.Byte[] hash;
```

- `private System.Byte[] embedded_source`  

```csharp
private System.Byte[] embedded_source;
```


## Properties

- `public System.String Url { get; set }`  

```csharp
public System.String Url { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.DocumentType Type { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.DocumentType Type { get; set; }
```

- `public System.Guid TypeGuid { get; set }`  

```csharp
public System.Guid TypeGuid { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.DocumentHashAlgorithm HashAlgorithm { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.DocumentHashAlgorithm HashAlgorithm { get; set; }
```

- `public System.Guid HashAlgorithmGuid { get; set }`  

```csharp
public System.Guid HashAlgorithmGuid { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.DocumentLanguage Language { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.DocumentLanguage Language { get; set; }
```

- `public System.Guid LanguageGuid { get; set }`  

```csharp
public System.Guid LanguageGuid { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.DocumentLanguageVendor LanguageVendor { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.DocumentLanguageVendor LanguageVendor { get; set; }
```

- `public System.Guid LanguageVendorGuid { get; set }`  

```csharp
public System.Guid LanguageVendorGuid { get; set; }
```

- `public System.Byte[] Hash { get; set }`  

```csharp
public System.Byte[] Hash { get; set; }
```

- `public System.Byte[] EmbeddedSource { get; set }`  

```csharp
public System.Byte[] EmbeddedSource { get; set; }
```


## Constructors

- `public Document(System.String url)`  

```csharp
public Document(System.String url);
```


