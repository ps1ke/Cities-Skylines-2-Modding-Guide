# Colossal.OdinSerializer.UnitySerializationUtility

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class UnitySerializationUtility
{
    public static readonly System.Type SerializeReferenceAttributeType;
    private static readonly System.Reflection.Assembly String_Assembly;
    private static readonly System.Reflection.Assembly HashSet_Assembly;
    private static readonly System.Reflection.Assembly LinkedList_Assembly;
    private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.Utilities.WeakValueGetter> UnityMemberGetters;
    private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.Utilities.WeakValueSetter> UnityMemberSetters;
    private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, System.Boolean> UnityWillSerializeMembersCache;
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.Boolean> UnityWillSerializeTypesCache;
    private static readonly System.Collections.Generic.HashSet<System.Type> UnityNeverSerializesTypes;
    private static readonly System.Collections.Generic.HashSet<System.String> UnityNeverSerializesTypeNames;
    private static readonly Colossal.OdinSerializer.ISerializationPolicy UnityPolicy;
    private static readonly Colossal.OdinSerializer.ISerializationPolicy EverythingPolicy;
    private static readonly Colossal.OdinSerializer.ISerializationPolicy StrictPolicy;
    private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult> OdinWillSerializeCache_UnityPolicy;
    private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult> OdinWillSerializeCache_EverythingPolicy;
    private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult> OdinWillSerializeCache_StrictPolicy;
    private static readonly System.Collections.Generic.Dictionary<Colossal.OdinSerializer.ISerializationPolicy, System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult>> OdinWillSerializeCache_CustomPolicies;

    private static System.Void ApplyPrefabModifications(UnityEngine.Object unityObject, System.Collections.Generic.List<System.String> modificationData, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects);
    private static System.Boolean CalculateOdinWillSerialize(System.Reflection.MemberInfo member, System.Boolean serializeUnityFields, Colossal.OdinSerializer.ISerializationPolicy policy);
    public static System.Object CreateDefaultUnityInitializedObject(System.Type type);
    private static System.Object CreateDefaultUnityInitializedObject(System.Type type, System.Int32 depth);
    public static System.Collections.Generic.List<Colossal.OdinSerializer.PrefabModification> DeserializePrefabModifications(System.Collections.Generic.List<System.String> modifications, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects);
    public static System.Void DeserializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.SerializationData& data, Colossal.OdinSerializer.DeserializationContext context);
    private static System.Void DeserializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.SerializationData& data, Colossal.OdinSerializer.DeserializationContext context, System.Boolean isPrefabData, System.Collections.Generic.List<UnityEngine.Object> prefabInstanceUnityObjects);
    public static System.Void DeserializeUnityObject(UnityEngine.Object unityObject, System.String& base64Bytes, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context);
    public static System.Void DeserializeUnityObject(UnityEngine.Object unityObject, System.Byte[]& bytes, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context);
    public static System.Void DeserializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.IDataReader reader);
    private static Colossal.OdinSerializer.Utilities.WeakValueGetter GetCachedUnityMemberGetter(System.Reflection.MemberInfo member);
    private static Colossal.OdinSerializer.Utilities.WeakValueSetter GetCachedUnityMemberSetter(System.Reflection.MemberInfo member);
    private static Colossal.OdinSerializer.Utilities.ICache GetCachedUnityReader(Colossal.OdinSerializer.DataFormat format, System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context);
    private static Colossal.OdinSerializer.Utilities.ICache GetCachedUnityWriter(Colossal.OdinSerializer.DataFormat format, System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context);
    private static System.String GetStringFromStreamAndReset(System.IO.Stream stream);
    public static System.Boolean GuessIfUnityWillSerialize(System.Reflection.MemberInfo member);
    public static System.Boolean GuessIfUnityWillSerialize(System.Type type);
    private static System.Boolean GuessIfUnityWillSerializePrivate(System.Reflection.MemberInfo member);
    private static System.Boolean GuessIfUnityWillSerializePrivate(System.Type type);
    public static System.Boolean OdinWillSerialize(System.Reflection.MemberInfo member, System.Boolean serializeUnityFields, Colossal.OdinSerializer.ISerializationPolicy policy);
    public static System.Collections.Generic.List<System.String> SerializePrefabModifications(System.Collections.Generic.List<Colossal.OdinSerializer.PrefabModification> modifications, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects);
    public static System.Void SerializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.SerializationData& data, System.Boolean serializeUnityFields, Colossal.OdinSerializer.SerializationContext context);
    public static System.Void SerializeUnityObject(UnityEngine.Object unityObject, System.String& base64Bytes, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects, Colossal.OdinSerializer.DataFormat format, System.Boolean serializeUnityFields, Colossal.OdinSerializer.SerializationContext context);
    public static System.Void SerializeUnityObject(UnityEngine.Object unityObject, System.Byte[]& bytes, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects, Colossal.OdinSerializer.DataFormat format, System.Boolean serializeUnityFields, Colossal.OdinSerializer.SerializationContext context);
    public static System.Void SerializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.IDataWriter writer, System.Boolean serializeUnityFields);
}
```


## Fields

- `public static readonly System.Type SerializeReferenceAttributeType`  

```csharp
public static readonly System.Type SerializeReferenceAttributeType;
```

- `private static readonly System.Reflection.Assembly String_Assembly`  

```csharp
private static readonly System.Reflection.Assembly String_Assembly;
```

- `private static readonly System.Reflection.Assembly HashSet_Assembly`  

```csharp
private static readonly System.Reflection.Assembly HashSet_Assembly;
```

- `private static readonly System.Reflection.Assembly LinkedList_Assembly`  

```csharp
private static readonly System.Reflection.Assembly LinkedList_Assembly;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.Utilities.WeakValueGetter> UnityMemberGetters`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.Utilities.WeakValueGetter> UnityMemberGetters;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.Utilities.WeakValueSetter> UnityMemberSetters`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.Utilities.WeakValueSetter> UnityMemberSetters;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, System.Boolean> UnityWillSerializeMembersCache`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, System.Boolean> UnityWillSerializeMembersCache;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Boolean> UnityWillSerializeTypesCache`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.Boolean> UnityWillSerializeTypesCache;
```

- `private static readonly System.Collections.Generic.HashSet<System.Type> UnityNeverSerializesTypes`  

```csharp
private static readonly System.Collections.Generic.HashSet<System.Type> UnityNeverSerializesTypes;
```

- `private static readonly System.Collections.Generic.HashSet<System.String> UnityNeverSerializesTypeNames`  

```csharp
private static readonly System.Collections.Generic.HashSet<System.String> UnityNeverSerializesTypeNames;
```

- `private static readonly Colossal.OdinSerializer.ISerializationPolicy UnityPolicy`  

```csharp
private static readonly Colossal.OdinSerializer.ISerializationPolicy UnityPolicy;
```

- `private static readonly Colossal.OdinSerializer.ISerializationPolicy EverythingPolicy`  

```csharp
private static readonly Colossal.OdinSerializer.ISerializationPolicy EverythingPolicy;
```

- `private static readonly Colossal.OdinSerializer.ISerializationPolicy StrictPolicy`  

```csharp
private static readonly Colossal.OdinSerializer.ISerializationPolicy StrictPolicy;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult> OdinWillSerializeCache_UnityPolicy`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult> OdinWillSerializeCache_UnityPolicy;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult> OdinWillSerializeCache_EverythingPolicy`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult> OdinWillSerializeCache_EverythingPolicy;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult> OdinWillSerializeCache_StrictPolicy`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult> OdinWillSerializeCache_StrictPolicy;
```

- `private static readonly System.Collections.Generic.Dictionary<Colossal.OdinSerializer.ISerializationPolicy, System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult>> OdinWillSerializeCache_CustomPolicies`  

```csharp
private static readonly System.Collections.Generic.Dictionary<Colossal.OdinSerializer.ISerializationPolicy, System.Collections.Generic.Dictionary<System.Reflection.MemberInfo, Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult>> OdinWillSerializeCache_CustomPolicies;
```


## Methods

- `private static ApplyPrefabModifications(UnityEngine.Object unityObject, System.Collections.Generic.List<System.String> modificationData, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects) : System.Void`  

```csharp
private static System.Void ApplyPrefabModifications(UnityEngine.Object unityObject, System.Collections.Generic.List<System.String> modificationData, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects);
```

- `private static CalculateOdinWillSerialize(System.Reflection.MemberInfo member, System.Boolean serializeUnityFields, Colossal.OdinSerializer.ISerializationPolicy policy) : System.Boolean`  

```csharp
private static System.Boolean CalculateOdinWillSerialize(System.Reflection.MemberInfo member, System.Boolean serializeUnityFields, Colossal.OdinSerializer.ISerializationPolicy policy);
```

- `public static CreateDefaultUnityInitializedObject(System.Type type) : System.Object`  

```csharp
public static System.Object CreateDefaultUnityInitializedObject(System.Type type);
```

- `private static CreateDefaultUnityInitializedObject(System.Type type, System.Int32 depth) : System.Object`  

```csharp
private static System.Object CreateDefaultUnityInitializedObject(System.Type type, System.Int32 depth);
```

- `public static DeserializePrefabModifications(System.Collections.Generic.List<System.String> modifications, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects) : System.Collections.Generic.List<Colossal.OdinSerializer.PrefabModification>`  

```csharp
public static System.Collections.Generic.List<Colossal.OdinSerializer.PrefabModification> DeserializePrefabModifications(System.Collections.Generic.List<System.String> modifications, System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects);
```

- `public static DeserializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.SerializationData& data, Colossal.OdinSerializer.DeserializationContext context = null) : System.Void`  

```csharp
public static System.Void DeserializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.SerializationData& data, Colossal.OdinSerializer.DeserializationContext context);
```

- `private static DeserializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.SerializationData& data, Colossal.OdinSerializer.DeserializationContext context, System.Boolean isPrefabData, System.Collections.Generic.List<UnityEngine.Object> prefabInstanceUnityObjects) : System.Void`  

```csharp
private static System.Void DeserializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.SerializationData& data, Colossal.OdinSerializer.DeserializationContext context, System.Boolean isPrefabData, System.Collections.Generic.List<UnityEngine.Object> prefabInstanceUnityObjects);
```

- `public static DeserializeUnityObject(UnityEngine.Object unityObject, System.String& base64Bytes, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context = null) : System.Void`  

```csharp
public static System.Void DeserializeUnityObject(UnityEngine.Object unityObject, System.String& base64Bytes, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context);
```

- `public static DeserializeUnityObject(UnityEngine.Object unityObject, System.Byte[]& bytes, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context = null) : System.Void`  

```csharp
public static System.Void DeserializeUnityObject(UnityEngine.Object unityObject, System.Byte[]& bytes, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects, Colossal.OdinSerializer.DataFormat format, Colossal.OdinSerializer.DeserializationContext context);
```

- `public static DeserializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
public static System.Void DeserializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.IDataReader reader);
```

- `private static GetCachedUnityMemberGetter(System.Reflection.MemberInfo member) : Colossal.OdinSerializer.Utilities.WeakValueGetter`  

```csharp
private static Colossal.OdinSerializer.Utilities.WeakValueGetter GetCachedUnityMemberGetter(System.Reflection.MemberInfo member);
```

- `private static GetCachedUnityMemberSetter(System.Reflection.MemberInfo member) : Colossal.OdinSerializer.Utilities.WeakValueSetter`  

```csharp
private static Colossal.OdinSerializer.Utilities.WeakValueSetter GetCachedUnityMemberSetter(System.Reflection.MemberInfo member);
```

- `private static GetCachedUnityReader(Colossal.OdinSerializer.DataFormat format, System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context) : Colossal.OdinSerializer.Utilities.ICache`  

```csharp
private static Colossal.OdinSerializer.Utilities.ICache GetCachedUnityReader(Colossal.OdinSerializer.DataFormat format, System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context);
```

- `private static GetCachedUnityWriter(Colossal.OdinSerializer.DataFormat format, System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context) : Colossal.OdinSerializer.Utilities.ICache`  

```csharp
private static Colossal.OdinSerializer.Utilities.ICache GetCachedUnityWriter(Colossal.OdinSerializer.DataFormat format, System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context);
```

- `private static GetStringFromStreamAndReset(System.IO.Stream stream) : System.String`  

```csharp
private static System.String GetStringFromStreamAndReset(System.IO.Stream stream);
```

- `public static GuessIfUnityWillSerialize(System.Reflection.MemberInfo member) : System.Boolean`  

```csharp
public static System.Boolean GuessIfUnityWillSerialize(System.Reflection.MemberInfo member);
```

- `public static GuessIfUnityWillSerialize(System.Type type) : System.Boolean`  

```csharp
public static System.Boolean GuessIfUnityWillSerialize(System.Type type);
```

- `private static GuessIfUnityWillSerializePrivate(System.Reflection.MemberInfo member) : System.Boolean`  

```csharp
private static System.Boolean GuessIfUnityWillSerializePrivate(System.Reflection.MemberInfo member);
```

- `private static GuessIfUnityWillSerializePrivate(System.Type type) : System.Boolean`  

```csharp
private static System.Boolean GuessIfUnityWillSerializePrivate(System.Type type);
```

- `public static OdinWillSerialize(System.Reflection.MemberInfo member, System.Boolean serializeUnityFields, Colossal.OdinSerializer.ISerializationPolicy policy = null) : System.Boolean`  

```csharp
public static System.Boolean OdinWillSerialize(System.Reflection.MemberInfo member, System.Boolean serializeUnityFields, Colossal.OdinSerializer.ISerializationPolicy policy);
```

- `public static SerializePrefabModifications(System.Collections.Generic.List<Colossal.OdinSerializer.PrefabModification> modifications, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects) : System.Collections.Generic.List<System.String>`  

```csharp
public static System.Collections.Generic.List<System.String> SerializePrefabModifications(System.Collections.Generic.List<Colossal.OdinSerializer.PrefabModification> modifications, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects);
```

- `public static SerializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.SerializationData& data, System.Boolean serializeUnityFields = False, Colossal.OdinSerializer.SerializationContext context = null) : System.Void`  

```csharp
public static System.Void SerializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.SerializationData& data, System.Boolean serializeUnityFields, Colossal.OdinSerializer.SerializationContext context);
```

- `public static SerializeUnityObject(UnityEngine.Object unityObject, System.String& base64Bytes, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects, Colossal.OdinSerializer.DataFormat format, System.Boolean serializeUnityFields = False, Colossal.OdinSerializer.SerializationContext context = null) : System.Void`  

```csharp
public static System.Void SerializeUnityObject(UnityEngine.Object unityObject, System.String& base64Bytes, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects, Colossal.OdinSerializer.DataFormat format, System.Boolean serializeUnityFields, Colossal.OdinSerializer.SerializationContext context);
```

- `public static SerializeUnityObject(UnityEngine.Object unityObject, System.Byte[]& bytes, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects, Colossal.OdinSerializer.DataFormat format, System.Boolean serializeUnityFields = False, Colossal.OdinSerializer.SerializationContext context = null) : System.Void`  

```csharp
public static System.Void SerializeUnityObject(UnityEngine.Object unityObject, System.Byte[]& bytes, System.Collections.Generic.List`1[[UnityEngine.Object, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& referencedUnityObjects, Colossal.OdinSerializer.DataFormat format, System.Boolean serializeUnityFields, Colossal.OdinSerializer.SerializationContext context);
```

- `public static SerializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.IDataWriter writer, System.Boolean serializeUnityFields = False) : System.Void`  

```csharp
public static System.Void SerializeUnityObject(UnityEngine.Object unityObject, Colossal.OdinSerializer.IDataWriter writer, System.Boolean serializeUnityFields);
```


## Nested types

- `Colossal.OdinSerializer.UnitySerializationUtility+CachedSerializationBackendResult`  
- `Colossal.OdinSerializer.UnitySerializationUtility+<>c`  
- `Colossal.OdinSerializer.UnitySerializationUtility+<>c__DisplayClass39_0`  
- `Colossal.OdinSerializer.UnitySerializationUtility+<>c__DisplayClass40_0`  

