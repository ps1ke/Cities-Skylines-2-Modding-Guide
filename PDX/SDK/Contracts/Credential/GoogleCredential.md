# PDX.SDK.Contracts.Credential.GoogleCredential

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Credential`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Credential.ICredential`  

## Code

```csharp
public class GoogleCredential : PDX.SDK.Contracts.Credential.ICredential
{
    private System.String <IdToken>k__BackingField;

    public System.String IdToken { get; set; }

    public GoogleCredential();
    public GoogleCredential(System.String idToken);

}
```


## Fields

- `private System.String <IdToken>k__BackingField`  

```csharp
private System.String <IdToken>k__BackingField;
```


## Properties

- `public System.String IdToken { get; set }`  

```csharp
public System.String IdToken { get; set; }
```


## Constructors

- `public GoogleCredential()`  

```csharp
public GoogleCredential();
```

- `public GoogleCredential(System.String idToken)`  

```csharp
public GoogleCredential(System.String idToken);
```


