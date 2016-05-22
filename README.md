# docs
SmartThings IDoT Service Documentation

## Smartthings Hackathon Ideas
* [Problem Domain](#focus)
* [iF IDoT Architecture](#architecture)
* [SmartThings IDP Project](#idp-project)

## <a name="focus"></a>Problem Domain
* cloud connected devices
* identity of things
* bring your own identity

How can an IoT device be attached to a user?

How can **any** IoT device be attached to **any** user?

How can any IoT device be **shared** with multiple users?

Can an IoT device be treated as a "user agent" posting events **on behalf of** user?

So, all "instances" of an IoT device have same device ID (do not need serial numbers to identify individual device instances). An instance of a device gets associated with a user as part of "on boarding" and gets an access token that uniquely identifies this association.

From that point onwards, all user -- device interactions use the device's access token as reference (or API key).

There will be separate access token for actual "app" (e.g. SmartApp) that will need to be authorized by the user to work with the device that has been associated with the user.

## <a name="architecture"></a>iF IDoT Architecture
![IDoT](https://github.com/SmartThingsIDoT/docs/blob/master/img/SmartThings_IDoT.jpg)

## <a name="idp-project"></a>SmartThings IDP Project
### Project Registration
* project ID : `e2ecd93f-aada-4009-8be1-4fa072c97749`

### Project Applications
* [SmartThings IDoT Service](#idot-service) backend app ID : `b36d560e-8149-42fa-bb41-0d24e1964bb6`
* [SmartThings IDoT Client](#idot-client) client app ID : `7204ae71-c0aa-446a-ae12-460afba58bf4`

### Custom Roles
Define custom roles for device control:

| ROLE | Description |
|------|-------------|
|`OPERATION` | user can onboard, control and view a device |
|`PATIENT` | user can control and view a device |
|`VIEWER`| user can only read device status |

### <a name="invite-users"></a>Invite Users
For the purpose of hackathon, we'll rely on explicit user invitation with fixed roles for demo. In real-world implementation, the owner of a device will "[share](#op-share-device)" the device with friend's identity and specify actions allowed on that "share".

* invite a user with custom role `OPERATION` who can onboard devices
* invite 2 users with custom role `PATIENT` who can control devices
* invite another user with custom role `VIEWER` who can only view status of devices
