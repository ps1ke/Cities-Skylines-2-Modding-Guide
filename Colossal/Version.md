# Colossal.Version

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.Version>`, `System.IComparable<Colossal.Version>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Version : System.IEquatable<Colossal.Version>, System.IComparable<Colossal.Version>, Colossal.Serialization.Entities.ISerializable
{
    private System.Byte m_VersionVersion;
    private System.Int64 m_Version;
    private System.Int32 m_VersionExtra;
    private static readonly Colossal.Version+OffsetSize[] kByteOffsetsSizes;
    private static readonly System.Char[] kReleaseTypeCode;
    private static System.Reflection.Assembly s_MainAssembly;
    public static const System.Byte kVersionFormat;

    public System.String shortVersion { get; }
    public System.String version { get; }
    public System.String fullVersion { get; }
    public System.UInt16 buildFarmNumber { get; }
    public System.UInt16 changesetNumber { get; }
    public System.Byte majorVersion { get; }
    public System.Byte minorVersion { get; }
    public System.Byte buildVersion { get; }
    public System.Char releaseType { get; }
    public System.Byte incrementalVersion { get; }

    public Version(System.Byte versionVersion, System.Int64 version, System.Int32 versionExtra);
    public Version(System.String version);

    public System.Int32 CompareTo(System.Object version);
    public System.Int32 CompareTo(Colossal.Version v);
    public System.Void Deserialize<TReader>(TReader reader);
    public virtual System.Boolean Equals(System.Object obj);
    public System.Boolean Equals(Colossal.Version v);
    public System.UInt16 GetComponentNumber(Colossal.Version+VersionComponents component);
    public static Colossal.Version GetCurrent();
    public static Colossal.Version GetCurrent(System.Reflection.Assembly assembly);
    public static Colossal.Version GetCurrentFromMainAssembly();
    public static System.UInt16 GetDate();
    public virtual System.Int32 GetHashCode();
    public static Colossal.Version+ReleaseType GetReleaseType(System.Char letter);
    public static System.Char GetReleaseTypeLetter(Colossal.Version+ReleaseType type);
    public static System.UInt16 GetTime();
    public System.Void GetVersionInternal(System.Byte& versionVersion, System.Int64& version, System.Int32& versionExtra);
    private System.UInt16 ParseReleaseType(System.String substr);
    private System.UInt16 ParseUShort(System.String substr);
    private System.Void ParseVersion(System.String version);
    private System.UInt16 ReadComponent(Colossal.Version+VersionComponents component);
    private System.Void ReadVersionDataFromAssembly(System.Reflection.Assembly callingAssembly);
    public System.Void Serialize<TWriter>(TWriter writer);
    public virtual System.String ToString();
    public static System.UInt16 Validate(Colossal.Version+VersionComponents component, System.Int32 value);
    private System.Void WriteComponent(Colossal.Version+VersionComponents component, System.UInt16 value);
}
```


## Fields

- `private System.Byte m_VersionVersion`  

```csharp
private System.Byte m_VersionVersion;
```

- `private System.Int64 m_Version`  

```csharp
private System.Int64 m_Version;
```

- `private System.Int32 m_VersionExtra`  

```csharp
private System.Int32 m_VersionExtra;
```

- `private static readonly Colossal.Version+OffsetSize[] kByteOffsetsSizes`  

```csharp
private static readonly Colossal.Version+OffsetSize[] kByteOffsetsSizes;
```

- `private static readonly System.Char[] kReleaseTypeCode`  

```csharp
private static readonly System.Char[] kReleaseTypeCode;
```

- `private static System.Reflection.Assembly s_MainAssembly`  

```csharp
private static System.Reflection.Assembly s_MainAssembly;
```

- `public static const System.Byte kVersionFormat`  

```csharp
public static const System.Byte kVersionFormat;
```


## Properties

- `public System.String shortVersion { get }`  

```csharp
public System.String shortVersion { get; }
```

- `public System.String version { get }`  

```csharp
public System.String version { get; }
```

- `public System.String fullVersion { get }`  

```csharp
public System.String fullVersion { get; }
```

- `public System.UInt16 buildFarmNumber { get }`  

```csharp
public System.UInt16 buildFarmNumber { get; }
```

- `public System.UInt16 changesetNumber { get }`  

```csharp
public System.UInt16 changesetNumber { get; }
```

- `public System.Byte majorVersion { get }`  

```csharp
public System.Byte majorVersion { get; }
```

- `public System.Byte minorVersion { get }`  

```csharp
public System.Byte minorVersion { get; }
```

- `public System.Byte buildVersion { get }`  

```csharp
public System.Byte buildVersion { get; }
```

- `public System.Char releaseType { get }`  

```csharp
public System.Char releaseType { get; }
```

- `public System.Byte incrementalVersion { get }`  

```csharp
public System.Byte incrementalVersion { get; }
```


## Constructors

- `public Version(System.Byte versionVersion, System.Int64 version, System.Int32 versionExtra)`  

```csharp
public Version(System.Byte versionVersion, System.Int64 version, System.Int32 versionExtra);
```

- `public Version(System.String version)`  

```csharp
public Version(System.String version);
```


## Methods

- `public CompareTo(System.Object version) : System.Int32`  

```csharp
public System.Int32 CompareTo(System.Object version);
```

- `public CompareTo(Colossal.Version v) : System.Int32`  

```csharp
public System.Int32 CompareTo(Colossal.Version v);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public Equals(Colossal.Version v) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.Version v);
```

- `public GetComponentNumber(Colossal.Version+VersionComponents component) : System.UInt16`  

```csharp
public System.UInt16 GetComponentNumber(Colossal.Version+VersionComponents component);
```

- `public static GetCurrent() : Colossal.Version`  

```csharp
public static Colossal.Version GetCurrent();
```

- `public static GetCurrent(System.Reflection.Assembly assembly) : Colossal.Version`  

```csharp
public static Colossal.Version GetCurrent(System.Reflection.Assembly assembly);
```

- `public static GetCurrentFromMainAssembly() : Colossal.Version`  

```csharp
public static Colossal.Version GetCurrentFromMainAssembly();
```

- `public static GetDate() : System.UInt16`  

```csharp
public static System.UInt16 GetDate();
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public static GetReleaseType(System.Char letter) : Colossal.Version+ReleaseType`  

```csharp
public static Colossal.Version+ReleaseType GetReleaseType(System.Char letter);
```

- `public static GetReleaseTypeLetter(Colossal.Version+ReleaseType type) : System.Char`  

```csharp
public static System.Char GetReleaseTypeLetter(Colossal.Version+ReleaseType type);
```

- `public static GetTime() : System.UInt16`  

```csharp
public static System.UInt16 GetTime();
```

- `public GetVersionInternal(System.Byte& versionVersion, System.Int64& version, System.Int32& versionExtra) : System.Void`  

```csharp
public System.Void GetVersionInternal(System.Byte& versionVersion, System.Int64& version, System.Int32& versionExtra);
```

- `private ParseReleaseType(System.String substr) : System.UInt16`  

```csharp
private System.UInt16 ParseReleaseType(System.String substr);
```

- `private ParseUShort(System.String substr) : System.UInt16`  

```csharp
private System.UInt16 ParseUShort(System.String substr);
```

- `private ParseVersion(System.String version) : System.Void`  

```csharp
private System.Void ParseVersion(System.String version);
```

- `private ReadComponent(Colossal.Version+VersionComponents component) : System.UInt16`  

```csharp
private System.UInt16 ReadComponent(Colossal.Version+VersionComponents component);
```

- `private ReadVersionDataFromAssembly(System.Reflection.Assembly callingAssembly) : System.Void`  

```csharp
private System.Void ReadVersionDataFromAssembly(System.Reflection.Assembly callingAssembly);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `public static Validate(Colossal.Version+VersionComponents component, System.Int32 value) : System.UInt16`  

```csharp
public static System.UInt16 Validate(Colossal.Version+VersionComponents component, System.Int32 value);
```

- `private WriteComponent(Colossal.Version+VersionComponents component, System.UInt16 value) : System.Void`  

```csharp
private System.Void WriteComponent(Colossal.Version+VersionComponents component, System.UInt16 value);
```


## Nested types

- `Colossal.Version+ReleaseType`  
- `Colossal.Version+VersionComponents`  
- `Colossal.Version+OffsetSize`  

