[d1-websdk](../README.md) / DisplayCardTask

# Class: DisplayCardTask

This class exposes the following methods to:

- Retrieve and display end user's card metadata information.
- Retrieve virtual card artwork asset.
- Display full card details.

## Table of contents

### Methods

- [displayCardDetails](DisplayCardTask.md#displaycarddetails)
- [displayCardMetadata](DisplayCardTask.md#displaycardmetadata)
- [maskCardDetails](DisplayCardTask.md#maskcarddetails)

## Methods

### displayCardDetails

▸ **displayCardDetails**(): `Promise`\<`void`\>

This method displays all the card details.
`onStateChange` callback function will be called before and after the fetch card details API operation.

> **_NOTE:_** As the card holder name styling option is optional, the card holder name will only be displayed if it is set.

#### Returns

`Promise`\<`void`\>

---

### displayCardMetadata

▸ **displayCardMetadata**(`fetchAssets?`): `Promise`\<[`CardMetadata`](../interfaces/CardMetadata.md)\>

This method displays the last four digit of card PAN and card expiry date while masking the rest
of the card details. `onStateChange` callback function will be called before and after the fetch card metadata API operation.

> **_NOTE:_** This does not render the card art background. The application is required to manage the card image asset and position
> the card details' `<div>` elements accordingly. Following code snippet shows an example.

```html
<div class="card-container">
  <div id="d1-card-pan"></div>
  <div id="d1-card-exp"></div>
  <div id="d1-card-cvv"></div>
  <div id="d1-card-chn"></div>
  <!-- If card asset fetched from SDK, need to replace the `src` with the base64 encoded card asset payload -->
  <!-- Application can also choose to manage their own card assets, instead of fetching them from the SDK -->
  <img
    src="data:image/png;base64,<base64_encoded_asset>"
    style="width: 100%; object-fit: contain;"
  />
</div>
```

#### Parameters

| Name          | Type      | Default value | Description                                                                                             |
| :------------ | :-------- | :------------ | :------------------------------------------------------------------------------------------------------ |
| `fetchAssets` | `boolean` | `false`       | If set to true, card asset will be fetched and returned from D1 backend server in Base64 encoded format |

#### Returns

`Promise`\<[`CardMetadata`](../interfaces/CardMetadata.md)\>

---

### maskCardDetails

▸ **maskCardDetails**(): `Promise`\<`void`\>

This method masks sensitive card details with the `maskCharacter` value set in options. The state of the display
will be the same as when called `displayCardMetadata` where only the last four digits of card PAN and
expiry date will be shown.

#### Returns

`Promise`\<`void`\>
