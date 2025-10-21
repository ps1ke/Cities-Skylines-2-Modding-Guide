# Game.UI.Menu.ParadoxBindings+LoginFormData

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonReadable`  

## Code

```csharp
public class LoginFormData : Colossal.UI.Binding.IJsonReadable
{
    public System.String email;
    public System.String password;

    public LoginFormData();

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


## Constructors

- `public LoginFormData()`  

```csharp
public LoginFormData();
```


## Methods

- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
```


