# Colossal.Mono.Cecil.Rocks.DocCommentId

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Rocks`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class DocCommentId
{
    private System.Text.StringBuilder id;

    private DocCommentId();

    private System.Void <WriteArrayTypeSignature>b__15_0(Colossal.Mono.Cecil.ArrayDimension dimension);
    private System.Void <WriteParameters>b__9_0(Colossal.Mono.Cecil.ParameterDefinition p);
    public static System.String GetDocCommentId(Colossal.Mono.Cecil.IMemberDefinition member);
    private static System.Boolean IsConversionOperator(Colossal.Mono.Cecil.MethodDefinition self);
    public virtual System.String ToString();
    private System.Void WriteArrayTypeSignature(Colossal.Mono.Cecil.ArrayType type);
    private System.Void WriteDefinition(System.Char id, Colossal.Mono.Cecil.IMemberDefinition member);
    private System.Void WriteEvent(Colossal.Mono.Cecil.EventDefinition event);
    private System.Void WriteField(Colossal.Mono.Cecil.FieldDefinition field);
    private System.Void WriteFunctionPointerTypeSignature(Colossal.Mono.Cecil.FunctionPointerType type);
    private System.Void WriteGenericInstanceTypeSignature(Colossal.Mono.Cecil.GenericInstanceType type);
    private System.Void WriteItemName(System.String name);
    private System.Void WriteList<T>(System.Collections.Generic.IList<T> list, System.Action<T> action);
    private System.Void WriteMethod(Colossal.Mono.Cecil.MethodDefinition method);
    private System.Void WriteModiferTypeSignature(Colossal.Mono.Cecil.IModifierType type, System.Char id);
    private System.Void WriteParameters(System.Collections.Generic.IList<Colossal.Mono.Cecil.ParameterDefinition> parameters);
    private System.Void WriteProperty(Colossal.Mono.Cecil.PropertyDefinition property);
    private System.Void WriteReturnType(Colossal.Mono.Cecil.MethodDefinition method);
    private System.Void WriteType(Colossal.Mono.Cecil.TypeDefinition type);
    private System.Void WriteTypeFullName(Colossal.Mono.Cecil.TypeReference type, System.Boolean stripGenericArity);
    private System.Void WriteTypeSignature(Colossal.Mono.Cecil.TypeReference type);
}
```


## Fields

- `private System.Text.StringBuilder id`  

```csharp
private System.Text.StringBuilder id;
```


## Constructors

- `private DocCommentId()`  

```csharp
private DocCommentId();
```


## Methods

- `private <WriteArrayTypeSignature>b__15_0(Colossal.Mono.Cecil.ArrayDimension dimension) : System.Void`  

```csharp
private System.Void <WriteArrayTypeSignature>b__15_0(Colossal.Mono.Cecil.ArrayDimension dimension);
```

- `private <WriteParameters>b__9_0(Colossal.Mono.Cecil.ParameterDefinition p) : System.Void`  

```csharp
private System.Void <WriteParameters>b__9_0(Colossal.Mono.Cecil.ParameterDefinition p);
```

- `public static GetDocCommentId(Colossal.Mono.Cecil.IMemberDefinition member) : System.String`  

```csharp
public static System.String GetDocCommentId(Colossal.Mono.Cecil.IMemberDefinition member);
```

- `private static IsConversionOperator(Colossal.Mono.Cecil.MethodDefinition self) : System.Boolean`  

```csharp
private static System.Boolean IsConversionOperator(Colossal.Mono.Cecil.MethodDefinition self);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `private WriteArrayTypeSignature(Colossal.Mono.Cecil.ArrayType type) : System.Void`  

```csharp
private System.Void WriteArrayTypeSignature(Colossal.Mono.Cecil.ArrayType type);
```

- `private WriteDefinition(System.Char id, Colossal.Mono.Cecil.IMemberDefinition member) : System.Void`  

```csharp
private System.Void WriteDefinition(System.Char id, Colossal.Mono.Cecil.IMemberDefinition member);
```

- `private WriteEvent(Colossal.Mono.Cecil.EventDefinition event) : System.Void`  

```csharp
private System.Void WriteEvent(Colossal.Mono.Cecil.EventDefinition event);
```

- `private WriteField(Colossal.Mono.Cecil.FieldDefinition field) : System.Void`  

```csharp
private System.Void WriteField(Colossal.Mono.Cecil.FieldDefinition field);
```

- `private WriteFunctionPointerTypeSignature(Colossal.Mono.Cecil.FunctionPointerType type) : System.Void`  

```csharp
private System.Void WriteFunctionPointerTypeSignature(Colossal.Mono.Cecil.FunctionPointerType type);
```

- `private WriteGenericInstanceTypeSignature(Colossal.Mono.Cecil.GenericInstanceType type) : System.Void`  

```csharp
private System.Void WriteGenericInstanceTypeSignature(Colossal.Mono.Cecil.GenericInstanceType type);
```

- `private WriteItemName(System.String name) : System.Void`  

```csharp
private System.Void WriteItemName(System.String name);
```

- `private WriteList<T>(System.Collections.Generic.IList<T> list, System.Action<T> action) : System.Void`  

```csharp
private System.Void WriteList<T>(System.Collections.Generic.IList<T> list, System.Action<T> action);
```

- `private WriteMethod(Colossal.Mono.Cecil.MethodDefinition method) : System.Void`  

```csharp
private System.Void WriteMethod(Colossal.Mono.Cecil.MethodDefinition method);
```

- `private WriteModiferTypeSignature(Colossal.Mono.Cecil.IModifierType type, System.Char id) : System.Void`  

```csharp
private System.Void WriteModiferTypeSignature(Colossal.Mono.Cecil.IModifierType type, System.Char id);
```

- `private WriteParameters(System.Collections.Generic.IList<Colossal.Mono.Cecil.ParameterDefinition> parameters) : System.Void`  

```csharp
private System.Void WriteParameters(System.Collections.Generic.IList<Colossal.Mono.Cecil.ParameterDefinition> parameters);
```

- `private WriteProperty(Colossal.Mono.Cecil.PropertyDefinition property) : System.Void`  

```csharp
private System.Void WriteProperty(Colossal.Mono.Cecil.PropertyDefinition property);
```

- `private WriteReturnType(Colossal.Mono.Cecil.MethodDefinition method) : System.Void`  

```csharp
private System.Void WriteReturnType(Colossal.Mono.Cecil.MethodDefinition method);
```

- `private WriteType(Colossal.Mono.Cecil.TypeDefinition type) : System.Void`  

```csharp
private System.Void WriteType(Colossal.Mono.Cecil.TypeDefinition type);
```

- `private WriteTypeFullName(Colossal.Mono.Cecil.TypeReference type, System.Boolean stripGenericArity = False) : System.Void`  

```csharp
private System.Void WriteTypeFullName(Colossal.Mono.Cecil.TypeReference type, System.Boolean stripGenericArity);
```

- `private WriteTypeSignature(Colossal.Mono.Cecil.TypeReference type) : System.Void`  

```csharp
private System.Void WriteTypeSignature(Colossal.Mono.Cecil.TypeReference type);
```


