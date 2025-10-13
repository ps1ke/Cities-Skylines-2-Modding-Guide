# PDX.SDK.Contracts.Credential.PsnCredential

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Credential`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Credential.ICredential`  

## Code

```csharp
public class PsnCredential : PDX.SDK.Contracts.Credential.ICredential
{
    private System.String <AuthCode>k__BackingField;
    private System.Int32 <IssuerId>k__BackingField;

    public System.String AuthCode { get; set; }
    public System.Int32 IssuerId { get; set; }

    public PsnCredential();
    public PsnCredential(System.String authCode, System.Int32 issuerId);

}
```


## Fields

- `private System.String <AuthCode>k__BackingField`  

```csharp
private System.String <AuthCode>k__BackingField;
```

- `private System.Int32 <IssuerId>k__BackingField`  

```csharp
private System.Int32 <IssuerId>k__BackingField;
```


## Properties

- `public System.String AuthCode { get; set }`  

```csharp
public System.String AuthCode { get; set; }
```

- `public System.Int32 IssuerId { get; set }`  

```csharp
public System.Int32 IssuerId { get; set; }
```


## Constructors

- `public PsnCredential()`  

```csharp
public PsnCredential();
```

- `public PsnCredential(System.String authCode, System.Int32 issuerId)`  

```csharp
public PsnCredential(System.String authCode, System.Int32 issuerId);
```


