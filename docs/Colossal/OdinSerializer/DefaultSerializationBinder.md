# Colossal.OdinSerializer.DefaultSerializationBinder

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.TwoWaySerializationBinder`  

## Fields

- `private static readonly System.Object ASSEMBLY_LOOKUP_LOCK`  
- `private static readonly System.Collections.Generic.Dictionary<System.String, System.Reflection.Assembly> assemblyNameLookUp`  
- `private static readonly System.Collections.Generic.Dictionary<System.String, System.Type> customTypeNameToTypeBindings`  
- `private static readonly System.Object TYPETONAME_LOCK`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.String> nameMap`  
- `private static readonly System.Object NAMETOTYPE_LOCK`  
- `private static readonly System.Collections.Generic.Dictionary<System.String, System.Type> typeMap`  
- `private static readonly System.Object ASSEMBLY_REGISTER_QUEUE_LOCK`  
- `private static readonly System.Collections.Generic.List<System.Reflection.Assembly> assembliesQueuedForRegister`  
- `private static readonly System.Collections.Generic.List<System.AssemblyLoadEventArgs> assemblyLoadEventsQueuedForRegister`  

## Constructors

- `public DefaultSerializationBinder()`  

## Methods

- `public virtual BindToName(System.Type type, Colossal.OdinSerializer.DebugContext debugContext = null) : System.String`  
- `public virtual BindToType(System.String typeName, Colossal.OdinSerializer.DebugContext debugContext = null) : System.Type`  
- `public virtual ContainsType(System.String typeName) : System.Boolean`  
- `private ParseGenericAndOrArrayType(System.String typeName, Colossal.OdinSerializer.DebugContext debugContext) : System.Type`  
- `private static ParseName(System.String fullName, System.String& typeName, System.String& assemblyName) : System.Void`  
- `private ParseTypeName(System.String typeName, Colossal.OdinSerializer.DebugContext debugContext) : System.Type`  
- `private static Peek(System.String str, System.Int32 i, System.Int32 ahead) : System.Char`  
- `private static ReadGenericArg(System.String typeName, System.Int32& i, System.String& argName) : System.Boolean`  
- `private static RegisterAllQueuedAssembliesRepeating() : System.Void`  
- `private static RegisterAssembly(System.Reflection.Assembly assembly) : System.Void`  
- `private static RegisterQueuedAssemblies() : System.Boolean`  
- `private static RegisterQueuedAssemblyLoadEvents() : System.Boolean`  
- `private static TryParseGenericAndOrArrayTypeName(System.String typeName, System.String& actualTypeName, System.Boolean& isGeneric, System.Collections.Generic.List`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& genericArgNames, System.Boolean& isArray, System.Int32& arrayRank) : System.Boolean`  

## Nested types

- `Colossal.OdinSerializer.DefaultSerializationBinder+<>c`  

