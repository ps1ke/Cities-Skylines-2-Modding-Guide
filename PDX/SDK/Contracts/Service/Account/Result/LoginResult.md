# PDX.SDK.Contracts.Service.Account.Result.LoginResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Account.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class LoginResult : PDX.SDK.Contracts.Result
{
    private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Legal.Models.Document> <LegalDocuments>k__BackingField;
    private System.String <UserId>k__BackingField;
    private System.String <SessionToken>k__BackingField;
    private PDX.SDK.Contracts.Enums.TrustLevel <TrustLevel>k__BackingField;
    private PDX.SDK.Contracts.Service.Account.Result.ThirdPartyResult <ThirdParty>k__BackingField;

    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Legal.Models.Document> LegalDocuments { get; set; }
    public System.String UserId { get; set; }
    public System.String SessionToken { get; set; }
    public PDX.SDK.Contracts.Enums.TrustLevel TrustLevel { get; set; }
    public PDX.SDK.Contracts.Service.Account.Result.ThirdPartyResult ThirdParty { get; set; }

    public LoginResult();
    public LoginResult(PDX.SDK.Contracts.Service.Account.Result.LoginResult login);

}
```


## Fields

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Legal.Models.Document> <LegalDocuments>k__BackingField`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Legal.Models.Document> <LegalDocuments>k__BackingField;
```

- `private System.String <UserId>k__BackingField`  

```csharp
private System.String <UserId>k__BackingField;
```

- `private System.String <SessionToken>k__BackingField`  

```csharp
private System.String <SessionToken>k__BackingField;
```

- `private PDX.SDK.Contracts.Enums.TrustLevel <TrustLevel>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Enums.TrustLevel <TrustLevel>k__BackingField;
```

- `private PDX.SDK.Contracts.Service.Account.Result.ThirdPartyResult <ThirdParty>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Account.Result.ThirdPartyResult <ThirdParty>k__BackingField;
```


## Properties

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Legal.Models.Document> LegalDocuments { get; set }`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Legal.Models.Document> LegalDocuments { get; set; }
```

- `public System.String UserId { get; set }`  

```csharp
public System.String UserId { get; set; }
```

- `public System.String SessionToken { get; set }`  

```csharp
public System.String SessionToken { get; set; }
```

- `public PDX.SDK.Contracts.Enums.TrustLevel TrustLevel { get; set }`  

```csharp
public PDX.SDK.Contracts.Enums.TrustLevel TrustLevel { get; set; }
```

- `public PDX.SDK.Contracts.Service.Account.Result.ThirdPartyResult ThirdParty { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Account.Result.ThirdPartyResult ThirdParty { get; set; }
```


## Constructors

- `public LoginResult()`  

```csharp
public LoginResult();
```

- `public LoginResult(PDX.SDK.Contracts.Service.Account.Result.LoginResult login)`  

```csharp
public LoginResult(PDX.SDK.Contracts.Service.Account.Result.LoginResult login);
```


