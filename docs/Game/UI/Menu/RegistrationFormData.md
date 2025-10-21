# Game.UI.Menu.ParadoxBindings+RegistrationFormData

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonReadable`  

## Code

```csharp
public class RegistrationFormData : Colossal.UI.Binding.IJsonReadable
{
    public System.String email;
    public System.String password;
    public System.String country;
    public System.String dateOfBirth;
    public System.Boolean marketingPermission;

    public RegistrationFormData();

    public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
}
```


## Fields

- `public System.String email`  

```csharp
public System.String email;
```

- `public System.String password`  

```csharp
public System.String password;
```

- `public System.String country`  

```csharp
public System.String country;
```

- `public System.String dateOfBirth`  

```csharp
public System.String dateOfBirth;
```

- `public System.Boolean marketingPermission`  

```csharp
public System.Boolean marketingPermission;
```


## Constructors

- `public RegistrationFormData()`  

```csharp
public RegistrationFormData();
```


## Methods

- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
```


