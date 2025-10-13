# Colossal.Mono.Cecil.Rocks.MethodDefinitionRocks

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Rocks`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class MethodDefinitionRocks
{
    public static Colossal.Mono.Cecil.MethodDefinition GetBaseMethod(Colossal.Mono.Cecil.MethodDefinition self);
    private static Colossal.Mono.Cecil.MethodDefinition GetMatchingMethod(Colossal.Mono.Cecil.TypeDefinition type, Colossal.Mono.Cecil.MethodDefinition method);
    public static Colossal.Mono.Cecil.MethodDefinition GetOriginalBaseMethod(Colossal.Mono.Cecil.MethodDefinition self);
    private static Colossal.Mono.Cecil.TypeDefinition ResolveBaseType(Colossal.Mono.Cecil.TypeDefinition type);
}
```


## Methods

- `public static GetBaseMethod(Colossal.Mono.Cecil.MethodDefinition self) : Colossal.Mono.Cecil.MethodDefinition`  

```csharp
public static Colossal.Mono.Cecil.MethodDefinition GetBaseMethod(Colossal.Mono.Cecil.MethodDefinition self);
```

- `private static GetMatchingMethod(Colossal.Mono.Cecil.TypeDefinition type, Colossal.Mono.Cecil.MethodDefinition method) : Colossal.Mono.Cecil.MethodDefinition`  

```csharp
private static Colossal.Mono.Cecil.MethodDefinition GetMatchingMethod(Colossal.Mono.Cecil.TypeDefinition type, Colossal.Mono.Cecil.MethodDefinition method);
```

- `public static GetOriginalBaseMethod(Colossal.Mono.Cecil.MethodDefinition self) : Colossal.Mono.Cecil.MethodDefinition`  

```csharp
public static Colossal.Mono.Cecil.MethodDefinition GetOriginalBaseMethod(Colossal.Mono.Cecil.MethodDefinition self);
```

- `private static ResolveBaseType(Colossal.Mono.Cecil.TypeDefinition type) : Colossal.Mono.Cecil.TypeDefinition`  

```csharp
private static Colossal.Mono.Cecil.TypeDefinition ResolveBaseType(Colossal.Mono.Cecil.TypeDefinition type);
```


