# Colossal.PSI.Common.OnDeviceAssociationChangedEventHandler

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public OnDeviceAssociationChangedEventHandler(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(Colossal.PSI.Common.IDeviceAssociationSupport psi, Colossal.PSI.Common.DeviceAssociationChange change, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  
- `public virtual Invoke(Colossal.PSI.Common.IDeviceAssociationSupport psi, Colossal.PSI.Common.DeviceAssociationChange change) : System.Void`  

