# Colossal.OdinSerializer.FormatterUtilities

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class FormatterUtilities
{
    private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<Colossal.OdinSerializer.ISerializationPolicy, System.Type, System.Reflection.MemberInfo[]> MemberArrayCache;
    private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<Colossal.OdinSerializer.ISerializationPolicy, System.Type, System.Collections.Generic.Dictionary<System.String, System.Reflection.MemberInfo>> MemberMapCache;
    private static readonly System.Object LOCK;
    private static readonly System.Collections.Generic.HashSet<System.Type> PrimitiveArrayTypes;
    private static readonly System.Reflection.FieldInfo UnityObjectRuntimeErrorStringField;
    private static const System.String UnityObjectRuntimeErrorString;

    public static UnityEngine.Object CreateUnityNull(System.Type nullType, System.Type owningType);
    private static System.Void FindSerializableMembers(System.Type type, System.Collections.Generic.List<System.Reflection.MemberInfo> members, Colossal.OdinSerializer.ISerializationPolicy policy);
    private static System.Collections.Generic.Dictionary<System.String, System.Reflection.MemberInfo> FindSerializableMembersMap(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy);
    public static System.Type GetContainedType(System.Reflection.MemberInfo member);
    public static System.Object GetMemberValue(System.Reflection.MemberInfo member, System.Object obj);
    public static System.Reflection.MemberInfo GetPrivateMemberAlias(System.Reflection.MemberInfo member, System.String prefixString, System.String separatorString);
    public static System.Reflection.MemberInfo[] GetSerializableMembers(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy);
    public static System.Collections.Generic.Dictionary<System.String, System.Reflection.MemberInfo> GetSerializableMembersMap(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy);
    public static System.Boolean IsPrimitiveArrayType(System.Type type);
    public static System.Boolean IsPrimitiveType(System.Type type);
    private static System.Boolean MemberIsPrivate(System.Reflection.MemberInfo member);
    public static System.Void SetMemberValue(System.Reflection.MemberInfo member, System.Object obj, System.Object value);
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<Colossal.OdinSerializer.ISerializationPolicy, System.Type, System.Reflection.MemberInfo[]> MemberArrayCache`  

```csharp
private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<Colossal.OdinSerializer.ISerializationPolicy, System.Type, System.Reflection.MemberInfo[]> MemberArrayCache;
```

- `private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<Colossal.OdinSerializer.ISerializationPolicy, System.Type, System.Collections.Generic.Dictionary<System.String, System.Reflection.MemberInfo>> MemberMapCache`  

```csharp
private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<Colossal.OdinSerializer.ISerializationPolicy, System.Type, System.Collections.Generic.Dictionary<System.String, System.Reflection.MemberInfo>> MemberMapCache;
```

- `private static readonly System.Object LOCK`  

```csharp
private static readonly System.Object LOCK;
```

- `private static readonly System.Collections.Generic.HashSet<System.Type> PrimitiveArrayTypes`  

```csharp
private static readonly System.Collections.Generic.HashSet<System.Type> PrimitiveArrayTypes;
```

- `private static readonly System.Reflection.FieldInfo UnityObjectRuntimeErrorStringField`  

```csharp
private static readonly System.Reflection.FieldInfo UnityObjectRuntimeErrorStringField;
```

- `private static const System.String UnityObjectRuntimeErrorString`  

```csharp
private static const System.String UnityObjectRuntimeErrorString;
```


## Methods

- `public static CreateUnityNull(System.Type nullType, System.Type owningType) : UnityEngine.Object`  

```csharp
public static UnityEngine.Object CreateUnityNull(System.Type nullType, System.Type owningType);
```

- `private static FindSerializableMembers(System.Type type, System.Collections.Generic.List<System.Reflection.MemberInfo> members, Colossal.OdinSerializer.ISerializationPolicy policy) : System.Void`  

```csharp
private static System.Void FindSerializableMembers(System.Type type, System.Collections.Generic.List<System.Reflection.MemberInfo> members, Colossal.OdinSerializer.ISerializationPolicy policy);
```

- `private static FindSerializableMembersMap(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy) : System.Collections.Generic.Dictionary<System.String, System.Reflection.MemberInfo>`  

```csharp
private static System.Collections.Generic.Dictionary<System.String, System.Reflection.MemberInfo> FindSerializableMembersMap(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy);
```

- `public static GetContainedType(System.Reflection.MemberInfo member) : System.Type`  

```csharp
public static System.Type GetContainedType(System.Reflection.MemberInfo member);
```

- `public static GetMemberValue(System.Reflection.MemberInfo member, System.Object obj) : System.Object`  

```csharp
public static System.Object GetMemberValue(System.Reflection.MemberInfo member, System.Object obj);
```

- `public static GetPrivateMemberAlias(System.Reflection.MemberInfo member, System.String prefixString = null, System.String separatorString = null) : System.Reflection.MemberInfo`  

```csharp
public static System.Reflection.MemberInfo GetPrivateMemberAlias(System.Reflection.MemberInfo member, System.String prefixString, System.String separatorString);
```

- `public static GetSerializableMembers(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy) : System.Reflection.MemberInfo[]`  

```csharp
public static System.Reflection.MemberInfo[] GetSerializableMembers(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy);
```

- `public static GetSerializableMembersMap(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy) : System.Collections.Generic.Dictionary<System.String, System.Reflection.MemberInfo>`  

```csharp
public static System.Collections.Generic.Dictionary<System.String, System.Reflection.MemberInfo> GetSerializableMembersMap(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy);
```

- `public static IsPrimitiveArrayType(System.Type type) : System.Boolean`  

```csharp
public static System.Boolean IsPrimitiveArrayType(System.Type type);
```

- `public static IsPrimitiveType(System.Type type) : System.Boolean`  

```csharp
public static System.Boolean IsPrimitiveType(System.Type type);
```

- `private static MemberIsPrivate(System.Reflection.MemberInfo member) : System.Boolean`  

```csharp
private static System.Boolean MemberIsPrivate(System.Reflection.MemberInfo member);
```

- `public static SetMemberValue(System.Reflection.MemberInfo member, System.Object obj, System.Object value) : System.Void`  

```csharp
public static System.Void SetMemberValue(System.Reflection.MemberInfo member, System.Object obj, System.Object value);
```


## Nested types

- `Colossal.OdinSerializer.FormatterUtilities+<>c`  
- `Colossal.OdinSerializer.FormatterUtilities+<>c__DisplayClass16_0`  

