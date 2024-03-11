[d1-websdk](../README.md) / DisplayCardEventCallbacks

# Interface: DisplayCardEventCallbacks

## Table of contents

### Properties

- [onCopyToClipboard](DisplayCardEventCallbacks.md#oncopytoclipboard)
- [onStateChange](DisplayCardEventCallbacks.md#onstatechange)

## Properties

### onCopyToClipboard

• `Optional` **onCopyToClipboard**: (`field`: `"PAN"` \| `"CVV"` \| `"EXP"` \| `"CHN"`) => `void`

#### Type declaration

▸ (`field`): `void`

This callback function is invoked when the card information is copied to the clipboard via the copy button. This does not return the actual values.

##### Parameters

| Name    | Type                                     | Description                                    |
| :------ | :--------------------------------------- | :--------------------------------------------- |
| `field` | `"PAN"` \| `"CVV"` \| `"EXP"` \| `"CHN"` | Indicates the card information that is copied. |

##### Returns

`void`

---

### onStateChange

• `Optional` **onStateChange**: (`state`: `"OP_FETCH_METADATA_START"` \| `"OP_FETCH_METADATA_STOP"` \| `"OP_DISPLAY_CARD_START"` \| `"OP_DISPLAY_CARD_STOP"`) => `void`

#### Type declaration

▸ (`state`): `void`

This callback function is invoked when the card metadata or card information are fetched from D1 backend server. The parameter has four possible state values:

1. `OP_FETCH_METADATA_START` - Indicates the start of the get card metadata operation.
2. `OP_FETCH_METADATA_STOP` - Indicates the end of the get card metadata operation.
3. `OP_DISPLAY_CARD_START` - Indicates the start of the get card details operation.
4. `OP_DISPLAY_CARD_STOP` -Indicates the end of the get card metadata operation.

##### Parameters

| Name    | Type                                                                                                               |
| :------ | :----------------------------------------------------------------------------------------------------------------- |
| `state` | `"OP_FETCH_METADATA_START"` \| `"OP_FETCH_METADATA_STOP"` \| `"OP_DISPLAY_CARD_START"` \| `"OP_DISPLAY_CARD_STOP"` |

##### Returns

`void`
