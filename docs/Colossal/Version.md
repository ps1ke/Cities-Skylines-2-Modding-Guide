# Colossal.Version

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.Version>`, `System.IComparable<Colossal.Version>`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `private System.Byte m_VersionVersion`  
- `private System.Int64 m_Version`  
- `private System.Int32 m_VersionExtra`  
- `private static readonly Colossal.Version+OffsetSize[] kByteOffsetsSizes`  
- `private static readonly System.Char[] kReleaseTypeCode`  
- `private static System.Reflection.Assembly s_MainAssembly`  
- `public static const System.Byte kVersionFormat`  

## Properties

- `public System.String shortVersion { get }`  
- `public System.String version { get }`  
- `public System.String fullVersion { get }`  
- `public System.UInt16 buildFarmNumber { get }`  
- `public System.UInt16 changesetNumber { get }`  
- `public System.Byte majorVersion { get }`  
- `public System.Byte minorVersion { get }`  
- `public System.Byte buildVersion { get }`  
- `public System.Char releaseType { get }`  
- `public System.Byte incrementalVersion { get }`  

## Constructors

- `public Version(System.Byte versionVersion, System.Int64 version, System.Int32 versionExtra)`  
- `public Version(System.String version)`  

## Methods

- `public CompareTo(System.Object version) : System.Int32`  
- `public CompareTo(Colossal.Version v) : System.Int32`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public Equals(Colossal.Version v) : System.Boolean`  
- `public GetComponentNumber(Colossal.Version+VersionComponents component) : System.UInt16`  
- `public static GetCurrent() : Colossal.Version`  
- `public static GetCurrent(System.Reflection.Assembly assembly) : Colossal.Version`  
- `public static GetCurrentFromMainAssembly() : Colossal.Version`  
- `public static GetDate() : System.UInt16`  
- `public virtual GetHashCode() : System.Int32`  
- `public static GetReleaseType(System.Char letter) : Colossal.Version+ReleaseType`  
- `public static GetReleaseTypeLetter(Colossal.Version+ReleaseType type) : System.Char`  
- `public static GetTime() : System.UInt16`  
- `public GetVersionInternal(System.Byte& versionVersion, System.Int64& version, System.Int32& versionExtra) : System.Void`  
- `private ParseReleaseType(System.String substr) : System.UInt16`  
- `private ParseUShort(System.String substr) : System.UInt16`  
- `private ParseVersion(System.String version) : System.Void`  
- `private ReadComponent(Colossal.Version+VersionComponents component) : System.UInt16`  
- `private ReadVersionDataFromAssembly(System.Reflection.Assembly callingAssembly) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public virtual ToString() : System.String`  
- `public static Validate(Colossal.Version+VersionComponents component, System.Int32 value) : System.UInt16`  
- `private WriteComponent(Colossal.Version+VersionComponents component, System.UInt16 value) : System.Void`  

## Nested types

- `Colossal.Version+ReleaseType`  
- `Colossal.Version+VersionComponents`  
- `Colossal.Version+OffsetSize`  

