# Colossal.Reflection.Tests.ClassWithMembers

**Assembly:** `Colossal.Core.TestScenarios`  
**Namespace:** `Colossal.Reflection.Tests`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class ClassWithMembers
{
    public System.Int32 PublicField;
    private System.Int32 PrivateField;
    private System.Int32 <PublicProperty>k__BackingField;
    private System.Int32 <PrivateProperty>k__BackingField;
    public static System.String StaticField;
    private static System.String PrivateStaticField;

    public System.Int32 PublicProperty { get; set; }
    private System.Int32 PrivateProperty { private get; private set; }

    public ClassWithMembers();

    private System.Void PrivateMethod();
    private static System.Void PrivateStaticMethod();
    public System.Void PublicMethod();
    public static System.Void StaticMethod();
}
```


## Fields

- `public System.Int32 PublicField`  

```csharp
public System.Int32 PublicField;
```

- `private System.Int32 PrivateField`  

```csharp
private System.Int32 PrivateField;
```

- `private System.Int32 <PublicProperty>k__BackingField`  

```csharp
private System.Int32 <PublicProperty>k__BackingField;
```

- `private System.Int32 <PrivateProperty>k__BackingField`  

```csharp
private System.Int32 <PrivateProperty>k__BackingField;
```

- `public static System.String StaticField`  

```csharp
public static System.String StaticField;
```

- `private static System.String PrivateStaticField`  

```csharp
private static System.String PrivateStaticField;
```


## Properties

- `public System.Int32 PublicProperty { get; set }`  

```csharp
public System.Int32 PublicProperty { get; set; }
```

- `private System.Int32 PrivateProperty { private get; private set }`  

```csharp
private System.Int32 PrivateProperty { private get; private set; }
```


## Constructors

- `public ClassWithMembers()`  

```csharp
public ClassWithMembers();
```


## Methods

- `private PrivateMethod() : System.Void`  

```csharp
private System.Void PrivateMethod();
```

- `private static PrivateStaticMethod() : System.Void`  

```csharp
private static System.Void PrivateStaticMethod();
```

- `public PublicMethod() : System.Void`  

```csharp
public System.Void PublicMethod();
```

- `public static StaticMethod() : System.Void`  

```csharp
public static System.Void StaticMethod();
```


