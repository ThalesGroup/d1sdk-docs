[d1-websdk](../README.md) / D1Error

# Class: D1Error

## Hierarchy

- `Error`

  ↳ **`D1Error`**

## Table of contents

### Properties

- [message](D1Error.md#message)
- [name](D1Error.md#name)
- [stack](D1Error.md#stack)
- [prepareStackTrace](D1Error.md#preparestacktrace)
- [stackTraceLimit](D1Error.md#stacktracelimit)

### Methods

- [getErrorCode](D1Error.md#geterrorcode)
- [getErrorDetails](D1Error.md#geterrordetails)
- [captureStackTrace](D1Error.md#capturestacktrace)

## Properties

### message

• **message**: `string`

#### Inherited from

Error.message

---

### name

• **name**: `string`

#### Inherited from

Error.name

---

### stack

• `Optional` **stack**: `string`

#### Inherited from

Error.stack

---

### prepareStackTrace

▪ `Static` `Optional` **prepareStackTrace**: (`err`: `Error`, `stackTraces`: `CallSite`[]) => `any`

#### Type declaration

▸ (`err`, `stackTraces`): `any`

Optional override for formatting stack traces

##### Parameters

| Name          | Type         |
| :------------ | :----------- |
| `err`         | `Error`      |
| `stackTraces` | `CallSite`[] |

##### Returns

`any`

**`See`**

https://v8.dev/docs/stack-trace-api#customizing-stack-traces

#### Inherited from

Error.prepareStackTrace

---

### stackTraceLimit

▪ `Static` **stackTraceLimit**: `number`

#### Inherited from

Error.stackTraceLimit

## Methods

### getErrorCode

▸ **getErrorCode**(): `"FIELD_INVALID_VALUE"` \| `"NOT_LOGGED_IN"` \| `"NOT_AUTHORIZED"` \| `"WRONG_CONFIGURATION"` \| `"INTERNAL_ERROR"` \| `"UNKNOWN_ERROR"`

#### Returns

`"FIELD_INVALID_VALUE"` \| `"NOT_LOGGED_IN"` \| `"NOT_AUTHORIZED"` \| `"WRONG_CONFIGURATION"` \| `"INTERNAL_ERROR"` \| `"UNKNOWN_ERROR"`

---

### getErrorDetails

▸ **getErrorDetails**(): `undefined` \| `string`

#### Returns

`undefined` \| `string`

---

### captureStackTrace

▸ **captureStackTrace**(`targetObject`, `constructorOpt?`): `void`

Create .stack property on a target object

#### Parameters

| Name              | Type       |
| :---------------- | :--------- |
| `targetObject`    | `object`   |
| `constructorOpt?` | `Function` |

#### Returns

`void`

#### Inherited from

Error.captureStackTrace
