# HomekitGuide

## Getting Pairing Data from Keychain
Step 1: Dump `com.apple.hap.pairing` keychain data from macos keychain

Two Entries are important:
### HomeKit Pairing Identity
There might be multiple, so testing each might be necessary to find the correct one.
##### Account
Format: XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
-> This is the iOSDevicePairingID.
> For usage with `hap-controller-node`the entire string including the `-`, needs to be converted into a hexstring.

##### Key
This consists of the `<iOSDeviceLTPK>+<iOSDeviceLTSK>`
> For usage with `hap-controller-node`: iOSDeviceLTSK=`<iOSDeviceLTSK><iOSDeviceLTPK>`

### Paired HomeKit Accessory
##### Account
Format: XX:XX:XX:XX:XX:XX
-> This is the AccessoryPairingID.
> For usage with `hap-controller-node`the entire string including the `:`, needs to be converted into a hexstring.

##### Key
This is the AccessoryLTPK.




## Good too know

##### HAP-python
This library usually accepts the data in the format from the keychain
