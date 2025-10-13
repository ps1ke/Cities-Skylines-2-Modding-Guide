# Colossal.Mono.Cecil.Rocks.SecurityDeclarationRocks

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Rocks`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class SecurityDeclarationRocks
{
    private static System.Void CompleteSecurityAttribute(System.Security.Permissions.SecurityAttribute security_attribute, Colossal.Mono.Cecil.SecurityAttribute attribute);
    private static System.Void CompleteSecurityAttributeFields(System.Security.Permissions.SecurityAttribute security_attribute, Colossal.Mono.Cecil.SecurityAttribute attribute);
    private static System.Void CompleteSecurityAttributeProperties(System.Security.Permissions.SecurityAttribute security_attribute, Colossal.Mono.Cecil.SecurityAttribute attribute);
    private static System.Security.IPermission CreatePermission(Colossal.Mono.Cecil.SecurityDeclaration declaration, Colossal.Mono.Cecil.SecurityAttribute attribute);
    private static System.Security.PermissionSet CreatePermissionSet(Colossal.Mono.Cecil.SecurityDeclaration declaration);
    private static System.Security.Permissions.SecurityAttribute CreateSecurityAttribute(System.Type attribute_type, Colossal.Mono.Cecil.SecurityDeclaration declaration);
    public static System.Security.PermissionSet ToPermissionSet(Colossal.Mono.Cecil.SecurityDeclaration self);
    public static Colossal.Mono.Cecil.SecurityDeclaration ToSecurityDeclaration(System.Security.PermissionSet self, Colossal.Mono.Cecil.SecurityAction action, Colossal.Mono.Cecil.ModuleDefinition module);
    private static System.Boolean TryProcessPermissionSetAttribute(Colossal.Mono.Cecil.SecurityDeclaration declaration, System.Security.PermissionSet& set);
}
```


## Methods

- `private static CompleteSecurityAttribute(System.Security.Permissions.SecurityAttribute security_attribute, Colossal.Mono.Cecil.SecurityAttribute attribute) : System.Void`  

```csharp
private static System.Void CompleteSecurityAttribute(System.Security.Permissions.SecurityAttribute security_attribute, Colossal.Mono.Cecil.SecurityAttribute attribute);
```

- `private static CompleteSecurityAttributeFields(System.Security.Permissions.SecurityAttribute security_attribute, Colossal.Mono.Cecil.SecurityAttribute attribute) : System.Void`  

```csharp
private static System.Void CompleteSecurityAttributeFields(System.Security.Permissions.SecurityAttribute security_attribute, Colossal.Mono.Cecil.SecurityAttribute attribute);
```

- `private static CompleteSecurityAttributeProperties(System.Security.Permissions.SecurityAttribute security_attribute, Colossal.Mono.Cecil.SecurityAttribute attribute) : System.Void`  

```csharp
private static System.Void CompleteSecurityAttributeProperties(System.Security.Permissions.SecurityAttribute security_attribute, Colossal.Mono.Cecil.SecurityAttribute attribute);
```

- `private static CreatePermission(Colossal.Mono.Cecil.SecurityDeclaration declaration, Colossal.Mono.Cecil.SecurityAttribute attribute) : System.Security.IPermission`  

```csharp
private static System.Security.IPermission CreatePermission(Colossal.Mono.Cecil.SecurityDeclaration declaration, Colossal.Mono.Cecil.SecurityAttribute attribute);
```

- `private static CreatePermissionSet(Colossal.Mono.Cecil.SecurityDeclaration declaration) : System.Security.PermissionSet`  

```csharp
private static System.Security.PermissionSet CreatePermissionSet(Colossal.Mono.Cecil.SecurityDeclaration declaration);
```

- `private static CreateSecurityAttribute(System.Type attribute_type, Colossal.Mono.Cecil.SecurityDeclaration declaration) : System.Security.Permissions.SecurityAttribute`  

```csharp
private static System.Security.Permissions.SecurityAttribute CreateSecurityAttribute(System.Type attribute_type, Colossal.Mono.Cecil.SecurityDeclaration declaration);
```

- `public static ToPermissionSet(Colossal.Mono.Cecil.SecurityDeclaration self) : System.Security.PermissionSet`  

```csharp
public static System.Security.PermissionSet ToPermissionSet(Colossal.Mono.Cecil.SecurityDeclaration self);
```

- `public static ToSecurityDeclaration(System.Security.PermissionSet self, Colossal.Mono.Cecil.SecurityAction action, Colossal.Mono.Cecil.ModuleDefinition module) : Colossal.Mono.Cecil.SecurityDeclaration`  

```csharp
public static Colossal.Mono.Cecil.SecurityDeclaration ToSecurityDeclaration(System.Security.PermissionSet self, Colossal.Mono.Cecil.SecurityAction action, Colossal.Mono.Cecil.ModuleDefinition module);
```

- `private static TryProcessPermissionSetAttribute(Colossal.Mono.Cecil.SecurityDeclaration declaration, System.Security.PermissionSet& set) : System.Boolean`  

```csharp
private static System.Boolean TryProcessPermissionSetAttribute(Colossal.Mono.Cecil.SecurityDeclaration declaration, System.Security.PermissionSet& set);
```


