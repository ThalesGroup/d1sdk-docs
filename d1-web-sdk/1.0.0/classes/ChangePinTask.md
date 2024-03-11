[d1-websdk](../README.md) / ChangePinTask

# Class: ChangePinTask

This class exposes the following methods to

- Display change PIN UI
- Reset PIN values in UI
- Submit new card PIN

## Table of contents

### Methods

- [reset](ChangePinTask.md#reset)
- [showPinEntryUI](ChangePinTask.md#showpinentryui)
- [submit](ChangePinTask.md#submit)

## Methods

### reset

▸ **reset**(): `Promise`\<`void`\>

This method clears all the PIN input values

#### Returns

`Promise`\<`void`\>

---

### showPinEntryUI

▸ **showPinEntryUI**(): `Promise`\<`void`\>

This method renders the change PIN UI iframe according to the styles set in options.

#### Returns

`Promise`\<`void`\>

---

### submit

▸ **submit**(): `Promise`\<`void`\>

This method sends the PIN values input to the D1 back-end server to register a change in PIN.
If the `onSubmitPin` callback function is set, it will be executed before and after the submit API operation.

#### Returns

`Promise`\<`void`\>
