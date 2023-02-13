# User Authentication of IoT Devices using Blockchain-enabled Fog Nodes

## Introduction

- This contract will perform the user authentication of IoT devices using Blockchain-enabled Fog Nodes

## How to use

- Step 1: Copy code in file SmartContract.sol
- Step 2: Open Remix IDE, create new file name SmartContract.sol and paste this code
- Step 3: Open tab SOLIDITY COMPILER and compile file SmartContract.sol
- Step 4: Open tab DEPLOY & RUN TRANSACTIONS and deploy AuthenticationContract

## List function

### 1. Struct

- The information of a given token

```
struct Token {
        bytes32 UID;
        address user;
        address dev;
        address fog;
}
```

- The addresses of devices

```
struct Devices{
        address dev;
        address fog;
}
```

### 2. Variables

- Admins of the system

```
 address [] admins;
```

- Array of all tokens issued

```
 Token [] public Tokens ;
```

### 3. Mapping

- mapping for users and their accessable devices

```
mapping (address => Devices[]) public users_devices;
```

- mapping for devices at a fog node

```
mapping (address => address[]) public fog_devices;
```

### 4. Modifier

- Require only admin to use funtion

```
modifier onlyAdmin
```

### 5. Funtion

- Adding admin by other admins

```
function addAdmin(address newAdmin) public onlyAdmin
```

- Adding admin by other admins

```
function addAdmin(address newAdmin) public onlyAdmin
```

- Adds a device to a given user by admin

```
function addUserDeviceMapping(address user, address device,address fog) public onlyAdmin
```

- Adds a device to a given fog node

```
function addDeviceFogMapping(address fog, address device) public onlyAdmin
```

- Delete a given admin

```
function delAdmin (address admin) public onlyAdmin
```

- Delete user access to all devices

```
function delUser(address user) public onlyAdmin
```

- Delete devices at a fog node

```
function delDev(address fog) public onlyAdmin
```

- Authetnication request

```
function requestAuthentication(address device,address fog) public
```

