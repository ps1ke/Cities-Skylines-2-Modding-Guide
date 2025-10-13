# PDX.SDK.Contracts.Credential.EmailAndPasswordCredential

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Credential`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Credential.ICredential`  

## Code

```csharp
public class EmailAndPasswordCredential : PDX.SDK.Contracts.Credential.ICredential
{
    private System.String <Email>k__BackingField;
    private System.String <Password>k__BackingField;

    public System.String Email { get; set; }
    public System.String Password { get; set; }

    public EmailAndPasswordCredential(System.String email, System.String password);

}
```


## Fields

- `private System.String <Email>k__BackingField`  

```csharp
private System.String <Email>k__BackingField;
```

- `private System.String <Password>k__BackingField`  

```csharp
private System.String <Password>k__BackingField;
```


## Properties

- `public System.String Email { get; set }`  

```csharp
public System.String Email { get; set; }
```

- `public System.String Password { get; set }`  

```csharp
public System.String Password { get; set; }
```


## Constructors

- `public EmailAndPasswordCredential(System.String email, System.String password)`  

```csharp
public EmailAndPasswordCredential(System.String email, System.String password);
```


