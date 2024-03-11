d1-websdk

# d1-websdk

## Table of contents

### Classes

Main entry class:
- [D1WebSdkClient](classes/D1WebSdkClient.md)    

Other classes:
- [ChangePinTask](classes/ChangePinTask.md)
- [D1Error](classes/D1Error.md)
- [DisplayCardTask](classes/DisplayCardTask.md)

### Interfaces

- [BorderCssProperties](interfaces/BorderCssProperties.md)
- [CardAsset](interfaces/CardAsset.md)
- [CardAssetContent](interfaces/CardAssetContent.md)
- [CardMetadata](interfaces/CardMetadata.md)
- [ChangePinEventCallbacks](interfaces/ChangePinEventCallbacks.md)
- [ChangePinOptions](interfaces/ChangePinOptions.md)
- [ChangePinStyle](interfaces/ChangePinStyle.md)
- [ConfigureOptions](interfaces/ConfigureOptions.md)
- [CopyButtonCssProperties](interfaces/CopyButtonCssProperties.md)
- [DisplayCardCssProperties](interfaces/DisplayCardCssProperties.md)
- [DisplayCardEventCallbacks](interfaces/DisplayCardEventCallbacks.md)
- [DisplayCardOptions](interfaces/DisplayCardOptions.md)
- [ExpViewOptions](interfaces/ExpViewOptions.md)
- [PanViewOptions](interfaces/PanViewOptions.md)
- [PinContainerProperties](interfaces/PinContainerProperties.md)
- [PinCssProperties](interfaces/PinCssProperties.md)
- [ViewOptions](interfaces/ViewOptions.md)

### Type Aliases

- [DateFormat](README.md#dateformat)

### Variables

- [FIELD_INVALID_VALUE](README.md#field_invalid_value)
- [INTERNAL_ERROR](README.md#internal_error)
- [NOT_AUTHORIZED](README.md#not_authorized)
- [NOT_LOGGED_IN](README.md#not_logged_in)
- [UNKNOWN_ERROR](README.md#unknown_error)
- [WRONG_CONFIGURATION](README.md#wrong_configuration)

## Type Aliases

### DateFormat

Ƭ **DateFormat**: `"MM/YY"` \| `"YY/MM"` \| `"MM/YYYY"`

## Variables

### FIELD_INVALID_VALUE

• `Const` **FIELD_INVALID_VALUE**: `"FIELD_INVALID_VALUE"`

Malformed or invalid user input. For example, "pinLength must be between 4 and 8 inclusive".

---

### INTERNAL_ERROR

• `Const` **INTERNAL_ERROR**: `"INTERNAL_ERROR"`

An unrecoverable error occurred, could from be from third party libraries, D1 API, third party APIs etc.
Please open a support ticket for this error.

---

### NOT_AUTHORIZED

• `Const` **NOT_AUTHORIZED**: `"NOT_AUTHORIZED"`

Attempted operation is not authorized. Could be due to performing actions out of sequence.

---

### NOT_LOGGED_IN

• `Const` **NOT_LOGGED_IN**: `"NOT_LOGGED_IN"`

User is not logged in or the login validity has expired. Please prompt user to login again.

---

### UNKNOWN_ERROR

• `Const` **UNKNOWN_ERROR**: `"UNKNOWN_ERROR"`

An edge case error that shouldn't happen or an error that we did not anticipate.
Can retry the operation after some time, as the unknown error could be caused by ephemeral conditions like unstable network connection or server downtime.
If the error still persists, please open a support ticket.

---

### WRONG_CONFIGURATION

• `Const` **WRONG_CONFIGURATION**: `"WRONG_CONFIGURATION"`

Misconfiguration or missing configurations. Please open a support ticket for this error.
