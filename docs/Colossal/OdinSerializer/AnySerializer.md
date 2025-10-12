# Colossal.OdinSerializer.AnySerializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.Serializer`  

## Fields

- `private readonly System.Type SerializedType`  
- `private readonly System.Boolean IsEnum`  
- `private readonly System.Boolean IsValueType`  
- `private readonly System.Boolean MayBeBoxedValueType`  
- `private readonly System.Boolean IsAbstract`  
- `private readonly System.Boolean IsNullable`  
- `private readonly System.Boolean AllowDeserializeInvalidData`  
- `private Colossal.OdinSerializer.IFormatter UnityPolicyFormatter`  
- `private Colossal.OdinSerializer.IFormatter StrictPolicyFormatter`  
- `private Colossal.OdinSerializer.IFormatter EverythingPolicyFormatter`  
- `private readonly System.Collections.Generic.Dictionary<Colossal.OdinSerializer.ISerializationPolicy, Colossal.OdinSerializer.IFormatter> FormattersByPolicy`  
- `private readonly System.Object FormattersByPolicy_LOCK`  
- `private static readonly Colossal.OdinSerializer.ISerializationPolicy UnityPolicy`  
- `private static readonly Colossal.OdinSerializer.ISerializationPolicy StrictPolicy`  
- `private static readonly Colossal.OdinSerializer.ISerializationPolicy EverythingPolicy`  

## Constructors

- `public AnySerializer(System.Type serializedType)`  

## Methods

- `private GetBaseFormatter(Colossal.OdinSerializer.ISerializationPolicy serializationPolicy) : Colossal.OdinSerializer.IFormatter`  
- `public virtual ReadValueWeak(Colossal.OdinSerializer.IDataReader reader) : System.Object`  
- `public virtual WriteValueWeak(System.String name, System.Object value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

