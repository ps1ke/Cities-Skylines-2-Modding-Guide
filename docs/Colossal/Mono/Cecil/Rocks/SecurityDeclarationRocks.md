# Colossal.Mono.Cecil.Rocks.SecurityDeclarationRocks

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Rocks`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Methods

- `private static CompleteSecurityAttribute(System.Security.Permissions.SecurityAttribute security_attribute, Colossal.Mono.Cecil.SecurityAttribute attribute) : System.Void`  
- `private static CompleteSecurityAttributeFields(System.Security.Permissions.SecurityAttribute security_attribute, Colossal.Mono.Cecil.SecurityAttribute attribute) : System.Void`  
- `private static CompleteSecurityAttributeProperties(System.Security.Permissions.SecurityAttribute security_attribute, Colossal.Mono.Cecil.SecurityAttribute attribute) : System.Void`  
- `private static CreatePermission(Colossal.Mono.Cecil.SecurityDeclaration declaration, Colossal.Mono.Cecil.SecurityAttribute attribute) : System.Security.IPermission`  
- `private static CreatePermissionSet(Colossal.Mono.Cecil.SecurityDeclaration declaration) : System.Security.PermissionSet`  
- `private static CreateSecurityAttribute(System.Type attribute_type, Colossal.Mono.Cecil.SecurityDeclaration declaration) : System.Security.Permissions.SecurityAttribute`  
- `public static ToPermissionSet(Colossal.Mono.Cecil.SecurityDeclaration self) : System.Security.PermissionSet`  
- `public static ToSecurityDeclaration(System.Security.PermissionSet self, Colossal.Mono.Cecil.SecurityAction action, Colossal.Mono.Cecil.ModuleDefinition module) : Colossal.Mono.Cecil.SecurityDeclaration`  
- `private static TryProcessPermissionSetAttribute(Colossal.Mono.Cecil.SecurityDeclaration declaration, System.Security.PermissionSet& set) : System.Boolean`  

