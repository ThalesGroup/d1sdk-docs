[d1-websdk](../README.md) / ChangePinEventCallbacks

# Interface: ChangePinEventCallbacks

## Table of contents

### Properties

- [onChange](ChangePinEventCallbacks.md#onchange)
- [onMatch](ChangePinEventCallbacks.md#onmatch)
- [onMisMatch](ChangePinEventCallbacks.md#onmismatch)
- [onSubmitPin](ChangePinEventCallbacks.md#onsubmitpin)

## Properties

### onChange

• `Optional` **onChange**: () => `void`

#### Type declaration

▸ (): `void`

The callback function is invoked each time the PIN value changes.

##### Returns

`void`

---

### onMatch

• `Optional` **onMatch**: () => `void`

#### Type declaration

▸ (): `void`

This callback function is used when the PIN value matches the confirmed PIN value.

##### Returns

`void`

---

### onMisMatch

• `Optional` **onMisMatch**: () => `void`

#### Type declaration

▸ (): `void`

This callback function is used when the PIN value does not match the confirmed PIN value.

##### Returns

`void`

---

### onSubmitPin

• `Optional` **onSubmitPin**: (`state`: `"OP_SUBMIT_PIN_START"` \| `"OP_SUBMIT_PIN_STOP"`) => `void`

#### Type declaration

▸ (`state`): `void`

This callback function is invoked when the PIN entered is submitted to the D1 backend. The parameter has two possible state values:

1. `OP_SUBMIT_PIN_START` - When submit PIN operation starts
2. `OP_SUBMIT_PIN_STOP` - When submit PIN operation ends

##### Parameters

| Name    | Type                                              |
| :------ | :------------------------------------------------ |
| `state` | `"OP_SUBMIT_PIN_START"` \| `"OP_SUBMIT_PIN_STOP"` |

##### Returns

`void`
