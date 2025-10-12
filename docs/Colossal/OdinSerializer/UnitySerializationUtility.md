# Colossal.OdinSerializer.UnitySerializationUtility

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `public static readonly System.Type SerializeReferenceAttributeType`  
- `private static readonly System.Reflection.Assembly String_Assembly`  
- `private static readonly System.Reflection.Assembly HashSet_Assembly`  
- `private static readonly System.Reflection.Assembly LinkedList_Assembly`  
- `private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.Utilities.WeakValueGetter> UnityMemberGetters`  
- `private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.Utilities.WeakValueSetter> UnityMemberSetters`  
- `private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, System.Boolean> UnityWillSerializeMembersCache`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Boolean> UnityWillSerializeTypesCache`  
- `private static readonly System.Collections.Generic.HashSet<System.Type> UnityNeverSerializesTypes`  
- `private static readonly System.Collections.Generic.HashSet<System.String> UnityNeverSerializesTypeNames`  
- `private static readonly Colossal.OdinSerializer.ISerializationPolicy UnityPolicy`  
- `private static readonly Colossal.OdinSerializer.ISerializationPolicy EverythingPolicy`  
- `private static readonly Colossal.OdinSerializer.ISerializationPolicy StrictPolicy`  
- `private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult> OdinWillSerializeCache_UnityPolicy`  
- `private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult> OdinWillSerializeCache_EverythingPolicy`  
- `private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult> OdinWillSerializeCache_StrictPolicy`  
- `private static readonly System.Collections.Generic.Dictionary<Colossal.OdinSerializer.ISerializationPolicy, System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult>> OdinWillSerializeCache_CustomPolicies`  

## Methods

- `private static ApplyPrefabModifications(UnityEngine.Object unityObject, System.Collections.Generic.List<System.String> modificationData, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects) : System.Void`  
- `private static CalculateOdinWillSerialize(System.Reflection.MemberInfo member, System.Boolean serializeUnityFields, Colossal.OdinSerializer.ISerializationPolicy policy) : System.Boolean`  
- `public static CreateDefaultUnityInitializedObject(System.Type type) : System.Object`  
- `private static CreateDefaultUnityInitializedObject(System.Type type, System.Int32 depth) : System.Object`  
- `public static DeserializePrefabModifications(System.Collections.Generic.List<System.String> modifications, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects) : System.Collections.Generic.List<Colossal.OdinSerializer.PrefabModification>`  
- `public static DeserializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.SerializationData& data, Colossal.OdinSerializer.DeserializationContext context = null) : System.Void`  
- `private static DeserializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.SerializationData& data, Colossal.OdinSerializer.DeserializationContext context, System.Boolean isPrefabData, System.Collections.Generic.List<UnityEngine.Object> prefabInstanceUnityObjects) : System.Void`  
- `public static DeserializeUnityObject(UnityEngine.Object unityObject, System.String& base64Bytes, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context = null) : System.Void`  
- `public static DeserializeUnityObject(UnityEngine.Object unityObject, System.Byte[]& bytes, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context = null) : System.Void`  
- `public static DeserializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.IDataReader reader) : System.Void`  
- `private static GetCachedUnityMemberGetter(System.Reflection.MemberInfo member) : Colossal.OdinSerializer.Utilities.WeakValueGetter`  
- `private static GetCachedUnityMemberSetter(System.Reflection.MemberInfo member) : Colossal.OdinSerializer.Utilities.WeakValueSetter`  
- `private static GetCachedUnityReader(Colossal.OdinSerializer.DataFormat format, System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context) : Colossal.OdinSerializer.Utilities.ICache`  
- `private static GetCachedUnityWriter(Colossal.OdinSerializer.DataFormat format, System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context) : Colossal.OdinSerializer.Utilities.ICache`  
- `private static GetStringFromStreamAndReset(System.IO.Stream stream) : System.String`  
- `public static GuessIfUnityWillSerialize(System.Reflection.MemberInfo member) : System.Boolean`  
- `public static GuessIfUnityWillSerialize(System.Type type) : System.Boolean`  
- `private static GuessIfUnityWillSerializePrivate(System.Reflection.MemberInfo member) : System.Boolean`  
- `private static GuessIfUnityWillSerializePrivate(System.Type type) : System.Boolean`  
- `public static OdinWillSerialize(System.Reflection.MemberInfo member, System.Boolean serializeUnityFields, Colossal.OdinSerializer.ISerializationPolicy policy = null) : System.Boolean`  
- `public static SerializePrefabModifications(System.Collections.Generic.List<Colossal.OdinSerializer.PrefabModification> modifications, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects) : System.Collections.Generic.List<System.String>`  
- `public static SerializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.SerializationData& data, System.Boolean serializeUnityFields = False, Colossal.OdinSerializer.SerializationContext context = null) : System.Void`  
- `public static SerializeUnityObject(UnityEngine.Object unityObject, System.String& base64Bytes, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects, Colossal.OdinSerializer.DataFormat format, System.Boolean serializeUnityFields = False, Colossal.OdinSerializer.SerializationContext context = null) : System.Void`  
- `public static SerializeUnityObject(UnityEngine.Object unityObject, System.Byte[]& bytes, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects, Colossal.OdinSerializer.DataFormat format, System.Boolean serializeUnityFields = False, Colossal.OdinSerializer.SerializationContext context = null) : System.Void`  
- `public static SerializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.IDataWriter writer, System.Boolean serializeUnityFields = False) : System.Void`  

## Nested types

- `Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult`  
- `Colossal.OdinSerializer.UnitySerializationUtility+<>c`  
- `Colossal.OdinSerializer.UnitySerializationUtility+<>c__DisplayClass39_0`  
- `Colossal.OdinSerializer.UnitySerializationUtility+<>c__DisplayClass40_0`  

