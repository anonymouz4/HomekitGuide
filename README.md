# HomekitGuide

## Getting Pairing Data from Keychain
Step 1: Dump `com.apple.hap.pairing` keychain data from macos keychain

Follow [this guide](https://pvieito.com/2019/12/extract-homekit-pairing-keys)`.


To list the signing identities use `security find-identity -v`. Then take the text (not the hexnumber) including the quotation marks and run `export CODESIGNKIT_DEFAULT_IDENTITY="<text>"`

To show the keys, don't forget to add the `-v` to the swift run command.

––––––––––––––––––––––––––––

## Output

#### 1. HomeKit Pairing Identity
There might be multiple, so testing each might be necessary to find the correct one.
##### Account
Format: XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
-> This is the iOSDevicePairingID.
> For usage with `hap-controller-node`the entire string including the `-`, needs to be converted into a hexstring.

##### Key
This consists of the `<iOSDeviceLTPK>+<iOSDeviceLTSK>`
> For usage with `hap-controller-node`: iOSDeviceLTSK=`<iOSDeviceLTSK><iOSDeviceLTPK>`

#### 2. Paired HomeKit Accessory
##### Account
Format: XX:XX:XX:XX:XX:XX
-> This is the AccessoryPairingID.
> For usage with `hap-controller-node`the entire string including the `:`, needs to be converted into a hexstring.

##### Key
This is the AccessoryLTPK.




## Good too know

##### HAP-python
This library usually accepts the data in the format from the keychain
