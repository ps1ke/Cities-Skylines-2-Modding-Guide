# PDX.SDK.Contracts.Credential.XboxLiveCredential

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Credential`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Credential.ICredential`  

## Code

```csharp
public class XboxLiveCredential : PDX.SDK.Contracts.Credential.ICredential
{
    private System.String <Token>k__BackingField;
    private System.String <Signature>k__BackingField;

    public System.String Token { get; set; }
    public System.String Signature { get; set; }

    public XboxLiveCredential();
    public XboxLiveCredential(System.String token, System.String signature);

}
```


## Fields

- `private System.String <Token>k__BackingField`  

```csharp
private System.String <Token>k__BackingField;
```

- `private System.String <Signature>k__BackingField`  

```csharp
private System.String <Signature>k__BackingField;
```


## Properties

- `public System.String Token { get; set }`  

```csharp
public System.String Token { get; set; }
```

- `public System.String Signature { get; set }`  

```csharp
public System.String Signature { get; set; }
```


## Constructors

- `public XboxLiveCredential()`  

```csharp
public XboxLiveCredential();
```

- `public XboxLiveCredential(System.String token, System.String signature)`  

```csharp
public XboxLiveCredential(System.String token, System.String signature);
```


