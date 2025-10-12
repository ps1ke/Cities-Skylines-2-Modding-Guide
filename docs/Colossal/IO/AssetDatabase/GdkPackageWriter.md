# Colossal.IO.AssetDatabase.GdkPackageWriter

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.IPackageWriter`, `System.IDisposable`  

## Fields

- `private readonly Colossal.IO.AssetDatabase.GdkCloudDataSource m_DataSource`  
- `private readonly Colossal.PSI.MicrosoftGdk.GdkPlatform m_PlatformManager`  
- `private readonly System.String m_ContainerName`  
- `private readonly System.String m_ContainerGuidName`  
- `private readonly Colossal.Hash128 m_ContainerGuid`  
- `private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.GdkPackageWriter+Entry> m_Entries`  
- `private System.Boolean m_IsDirty`  

## Constructors

- `public GdkPackageWriter(Colossal.Hash128 id, Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi, Colossal.PSI.MicrosoftGdk.GdkPlatform platformManager, Colossal.IO.AssetDatabase.GdkCloudDataSource dataSource)`  

## Methods

- `public Add(Colossal.IO.AssetDatabase.IAssetData data, System.Boolean preserveTimestamp = False) : System.Void`  
- `private CheckPerUserQuota() : System.Boolean`  
- `public Commit() : System.Boolean`  
- `public Dispose() : System.Void`  

## Nested types

- `Colossal.IO.AssetDatabase.GdkPackageWriter+Entry`  

