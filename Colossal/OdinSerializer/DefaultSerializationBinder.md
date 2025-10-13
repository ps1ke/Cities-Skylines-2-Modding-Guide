# Colossal.OdinSerializer.DefaultSerializationBinder

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.TwoWaySerializationBinder`  

## Code

```csharp
public class DefaultSerializationBinder : Colossal.OdinSerializer.TwoWaySerializationBinder
{
    private static readonly System.Object ASSEMBLY_LOOKUP_LOCK;
    private static readonly System.Collections.Generic.Dictionary<System.String, System.Reflection.Assembly> assemblyNameLookUp;
    private static readonly System.Collections.Generic.Dictionary<System.String, System.Type> customTypeNameToTypeBindings;
    private static readonly System.Object TYPETONAME_LOCK;
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.String> nameMap;
    private static readonly System.Object NAMETOTYPE_LOCK;
    private static readonly System.Collections.Generic.Dictionary<System.String, System.Type> typeMap;
    private static readonly System.Object ASSEMBLY_REGISTER_QUEUE_LOCK;
    private static readonly System.Collections.Generic.List<System.Reflection.Assembly> assembliesQueuedForRegister;
    private static readonly System.Collections.Generic.List<System.AssemblyLoadEventArgs> assemblyLoadEventsQueuedForRegister;

    public DefaultSerializationBinder();

    public virtual System.String BindToName(System.Type type, Colossal.OdinSerializer.DebugContext debugContext);
    public virtual System.Type BindToType(System.String typeName, Colossal.OdinSerializer.DebugContext debugContext);
    public virtual System.Boolean ContainsType(System.String typeName);
    private System.Type ParseGenericAndOrArrayType(System.String typeName, Colossal.OdinSerializer.DebugContext debugContext);
    private static System.Void ParseName(System.String fullName, System.String& typeName, System.String& assemblyName);
    private System.Type ParseTypeName(System.String typeName, Colossal.OdinSerializer.DebugContext debugContext);
    private static System.Char Peek(System.String str, System.Int32 i, System.Int32 ahead);
    private static System.Boolean ReadGenericArg(System.String typeName, System.Int32& i, System.String& argName);
    private static System.Void RegisterAllQueuedAssembliesRepeating();
    private static System.Void RegisterAssembly(System.Reflection.Assembly assembly);
    private static System.Boolean RegisterQueuedAssemblies();
    private static System.Boolean RegisterQueuedAssemblyLoadEvents();
    private static System.Boolean TryParseGenericAndOrArrayTypeName(System.String typeName, System.String& actualTypeName, System.Boolean& isGeneric, System.Collections.Generic.List`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& genericArgNames, System.Boolean& isArray, System.Int32& arrayRank);
}
```


## Fields

- `private static readonly System.Object ASSEMBLY_LOOKUP_LOCK`  

```csharp
private static readonly System.Object ASSEMBLY_LOOKUP_LOCK;
```

- `private static readonly System.Collections.Generic.Dictionary<System.String, System.Reflection.Assembly> assemblyNameLookUp`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.String, System.Reflection.Assembly> assemblyNameLookUp;
```

- `private static readonly System.Collections.Generic.Dictionary<System.String, System.Type> customTypeNameToTypeBindings`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.String, System.Type> customTypeNameToTypeBindings;
```

- `private static readonly System.Object TYPETONAME_LOCK`  

```csharp
private static readonly System.Object TYPETONAME_LOCK;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.String> nameMap`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.String> nameMap;
```

- `private static readonly System.Object NAMETOTYPE_LOCK`  

```csharp
private static readonly System.Object NAMETOTYPE_LOCK;
```

- `private static readonly System.Collections.Generic.Dictionary<System.String, System.Type> typeMap`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.String, System.Type> typeMap;
```

- `private static readonly System.Object ASSEMBLY_REGISTER_QUEUE_LOCK`  

```csharp
private static readonly System.Object ASSEMBLY_REGISTER_QUEUE_LOCK;
```

- `private static readonly System.Collections.Generic.List<System.Reflection.Assembly> assembliesQueuedForRegister`  

```csharp
private static readonly System.Collections.Generic.List<System.Reflection.Assembly> assembliesQueuedForRegister;
```

- `private static readonly System.Collections.Generic.List<System.AssemblyLoadEventArgs> assemblyLoadEventsQueuedForRegister`  

```csharp
private static readonly System.Collections.Generic.List<System.AssemblyLoadEventArgs> assemblyLoadEventsQueuedForRegister;
```


## Constructors

- `public DefaultSerializationBinder()`  

```csharp
public DefaultSerializationBinder();
```


## Methods

- `public virtual BindToName(System.Type type, Colossal.OdinSerializer.DebugContext debugContext = null) : System.String`  

```csharp
public virtual System.String BindToName(System.Type type, Colossal.OdinSerializer.DebugContext debugContext);
```

- `public virtual BindToType(System.String typeName, Colossal.OdinSerializer.DebugContext debugContext = null) : System.Type`  

```csharp
public virtual System.Type BindToType(System.String typeName, Colossal.OdinSerializer.DebugContext debugContext);
```

- `public virtual ContainsType(System.String typeName) : System.Boolean`  

```csharp
public virtual System.Boolean ContainsType(System.String typeName);
```

- `private ParseGenericAndOrArrayType(System.String typeName, Colossal.OdinSerializer.DebugContext debugContext) : System.Type`  

```csharp
private System.Type ParseGenericAndOrArrayType(System.String typeName, Colossal.OdinSerializer.DebugContext debugContext);
```

- `private static ParseName(System.String fullName, System.String& typeName, System.String& assemblyName) : System.Void`  

```csharp
private static System.Void ParseName(System.String fullName, System.String& typeName, System.String& assemblyName);
```

- `private ParseTypeName(System.String typeName, Colossal.OdinSerializer.DebugContext debugContext) : System.Type`  

```csharp
private System.Type ParseTypeName(System.String typeName, Colossal.OdinSerializer.DebugContext debugContext);
```

- `private static Peek(System.String str, System.Int32 i, System.Int32 ahead) : System.Char`  

```csharp
private static System.Char Peek(System.String str, System.Int32 i, System.Int32 ahead);
```

- `private static ReadGenericArg(System.String typeName, System.Int32& i, System.String& argName) : System.Boolean`  

```csharp
private static System.Boolean ReadGenericArg(System.String typeName, System.Int32& i, System.String& argName);
```

- `private static RegisterAllQueuedAssembliesRepeating() : System.Void`  

```csharp
private static System.Void RegisterAllQueuedAssembliesRepeating();
```

- `private static RegisterAssembly(System.Reflection.Assembly assembly) : System.Void`  

```csharp
private static System.Void RegisterAssembly(System.Reflection.Assembly assembly);
```

- `private static RegisterQueuedAssemblies() : System.Boolean`  

```csharp
private static System.Boolean RegisterQueuedAssemblies();
```

- `private static RegisterQueuedAssemblyLoadEvents() : System.Boolean`  

```csharp
private static System.Boolean RegisterQueuedAssemblyLoadEvents();
```

- `private static TryParseGenericAndOrArrayTypeName(System.String typeName, System.String& actualTypeName, System.Boolean& isGeneric, System.Collections.Generic.List`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& genericArgNames, System.Boolean& isArray, System.Int32& arrayRank) : System.Boolean`  

```csharp
private static System.Boolean TryParseGenericAndOrArrayTypeName(System.String typeName, System.String& actualTypeName, System.Boolean& isGeneric, System.Collections.Generic.List`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& genericArgNames, System.Boolean& isArray, System.Int32& arrayRank);
```


## Nested types

- `Colossal.OdinSerializer.DefaultSerializationBinder+<>c`  

