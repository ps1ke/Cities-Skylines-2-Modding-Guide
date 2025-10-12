# Colossal.OdinSerializer.FormatterUtilities

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<Colossal.OdinSerializer.ISerializationPolicy, System.Type, System.Reflection.MemberInfo[]> MemberArrayCache`  
- `private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<Colossal.OdinSerializer.ISerializationPolicy, System.Type, System.Collections.Generic.Dictionary<System.String, System.Reflection.MemberInfo>> MemberMapCache`  
- `private static readonly System.Object LOCK`  
- `private static readonly System.Collections.Generic.HashSet<System.Type> PrimitiveArrayTypes`  
- `private static readonly System.Reflection.FieldInfo UnityObjectRuntimeErrorStringField`  
- `private static const System.String UnityObjectRuntimeErrorString`  

## Methods

- `public static CreateUnityNull(System.Type nullType, System.Type owningType) : UnityEngine.Object`  
- `private static FindSerializableMembers(System.Type type, System.Collections.Generic.List<System.Reflection.MemberInfo> members, Colossal.OdinSerializer.ISerializationPolicy policy) : System.Void`  
- `private static FindSerializableMembersMap(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy) : System.Collections.Generic.Dictionary<System.String, System.Reflection.MemberInfo>`  
- `public static GetContainedType(System.Reflection.MemberInfo member) : System.Type`  
- `public static GetMemberValue(System.Reflection.MemberInfo member, System.Object obj) : System.Object`  
- `public static GetPrivateMemberAlias(System.Reflection.MemberInfo member, System.String prefixString = null, System.String separatorString = null) : System.Reflection.MemberInfo`  
- `public static GetSerializableMembers(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy) : System.Reflection.MemberInfo[]`  
- `public static GetSerializableMembersMap(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy) : System.Collections.Generic.Dictionary<System.String, System.Reflection.MemberInfo>`  
- `public static IsPrimitiveArrayType(System.Type type) : System.Boolean`  
- `public static IsPrimitiveType(System.Type type) : System.Boolean`  
- `private static MemberIsPrivate(System.Reflection.MemberInfo member) : System.Boolean`  
- `public static SetMemberValue(System.Reflection.MemberInfo member, System.Object obj, System.Object value) : System.Void`  

## Nested types

- `Colossal.OdinSerializer.FormatterUtilities+<>c`  
- `Colossal.OdinSerializer.FormatterUtilities+<>c__DisplayClass16_0`  

