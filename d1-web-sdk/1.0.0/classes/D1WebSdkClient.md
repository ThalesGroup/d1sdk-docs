[d1-websdk](../README.md) / D1WebSdkClient

# Class: D1WebSdkClient

This class exposes D1 APIs to perform operations like display card details and change PIN.
Before proceeding with the operations, a configuration and authentication from this class are required.

**`Example`**

```ts
const d1WebSdkClient = new D1WebSdkClient();
d1WebSdkClient.configure({ issuerId: 'digibank01', consumerId: '123' });
await d1WebSdkClient.login(issuerToken);

// proceed to perform card related operations
```

## Table of contents

### Constructors

- [constructor](D1WebSdkClient.md#constructor)

### Methods

- [configure](D1WebSdkClient.md#configure)
- [createChangePinTask](D1WebSdkClient.md#createchangepintask)
- [createDisplayCardTask](D1WebSdkClient.md#createdisplaycardtask)
- [getSdkVersion](D1WebSdkClient.md#getsdkversion)
- [login](D1WebSdkClient.md#login)
- [logout](D1WebSdkClient.md#logout)
- [removeChangePinTask](D1WebSdkClient.md#removechangepintask)
- [removeDisplayCardTask](D1WebSdkClient.md#removedisplaycardtask)

## Constructors

### constructor

• **new D1WebSdkClient**(): [`D1WebSdkClient`](D1WebSdkClient.md)

#### Returns

[`D1WebSdkClient`](D1WebSdkClient.md)

## Methods

### configure

▸ **configure**(`options`): `void`

These are the configuration parameters that will be used throughout the lifecycle of the SDK object.

#### Parameters

| Name      | Type                                                    | Description                  |
| :-------- | :------------------------------------------------------ | :--------------------------- |
| `options` | [`ConfigureOptions`](../interfaces/ConfigureOptions.md) | Set of configuration options |

#### Returns

`void`

**`Example`**

```ts
d1WebSdkClient.configure({
  issuerId: 'YOUR_ISSUER_ID',
  consumerId: 'YOUR_CONSUMER_ID',
});
```

---

### createChangePinTask

▸ **createChangePinTask**(`changePinOptions`): [`ChangePinTask`](ChangePinTask.md)

This method is used to create the change PIN UI and a [ChangePinTask](ChangePinTask.md) singleton object.
The SDK will look for `<div>` elements with the following IDs and renders iframes within them
to display the corresponding PIN input:

- `d1-set-pin`
- `d1-confirm-pin`

> **_NOTE:_** Application must have `<div>` elements with IDs following the **exact** namings above for
> the iframes to be created.

For example, a `<div>` element with the `d1-set-pin` ID will have a nested iframe
to render the input element for the setting of new PIN. The following snippet shows how it appears in HTML format.

```html
<div id="d1-set-pin">
  <!-- created by application -->
  <iframe>
    <!-- created by SDK -->
    <html>
      <body>
        <input type="password" inputmode="numeric" />
        <!-- where end user will key their new PIN -->
      </body>
    </html>
  </iframe>
</div>
```

As such, it is the application's responsibility to arrange and position the element according
to its design or business requirements.

#### Parameters

| Name               | Type                                                    | Description                                                                                  |
| :----------------- | :------------------------------------------------------ | :------------------------------------------------------------------------------------------- |
| `changePinOptions` | [`ChangePinOptions`](../interfaces/ChangePinOptions.md) | Options to set card ID, PIN input length, styling options for the input boxes, and callbacks |

#### Returns

[`ChangePinTask`](ChangePinTask.md)

**`Example`**

```ts
const styles = {
  "digit": {
    "container": {
      "gap": "0px",
      "border": {
        "color": "#1c6da8",
        "radius": "4px",
        "width": "2px",
        "style": "solid"
      }
    },
    "main": {
      "height": "40px",
      "border": {
        "style": "none"
      },
      "margin": {},
      "padding": {}
    },
    "focus": {
      "border": {
        "color": "#0099ff"
      },
      "margin": {},
      "padding": {}
    }
  }
};

const changePinTask = d1WebSdkClient.createChangePinTask({
  cardId: 'YOUR_CARD_ID'
  pinLength: 4
  styles,
  eventCallbacks: {
    onMatch: () => {
      // tag notification, user input matches
    },
    onMisMatch: () => {
      // can reset PIN input when values mismatch
      this.resetPin();
      // tag notification, show error message
    },
    onSubmitPin: (state) => {
      if (state === 'OP_SUBMIT_PIN_STOP') {
        // start animation
      }
      if (state === 'OP_SUBMIT_PIN_STOP') {
        // stop animation
      }
    },
  },
});

// Now you will have access to additional change PIN methods
await changePinTask.showPinEntryUI();
await changePinTask.reset();
await changePinTask.submit();
```

---

### createDisplayCardTask

▸ **createDisplayCardTask**(`displayCardOptions`): [`DisplayCardTask`](DisplayCardTask.md)

This method is used to create the display card UI and a [DisplayCardTask](DisplayCardTask.md) singleton object.
The SDK will look for `<div>` elements with the following IDs and renders the iframes within the
elements to display the corresponding card detail:

- `d1-card-pan`
- `d1-card-exp`
- `d1-card-cvv`
- `d1-card-chn`

> **_NOTE:_** Application must have `<div>` elements with IDs following the **exact** namings above for
> the iframes to be created.

For example, a `<div>` element with the `d1-card-pan` ID will have a nested iframe
to display the card PAN. The following snippet shows how it appears in the HTML format.

```html
<div id="d1-card-pan">
  <!-- created by application -->
  <iframe>
    <!-- created by SDK -->
    <html>
      <body>
        <div>PAN_DIGITS</div>
      </body>
    </html>
  </iframe>
</div>
```

As such, it is the application's responsibility to arrange and position the element according
to its design or business requirements.

#### Parameters

| Name                 | Type                                                        | Description                                                                 |
| :------------------- | :---------------------------------------------------------- | :-------------------------------------------------------------------------- |
| `displayCardOptions` | [`DisplayCardOptions`](../interfaces/DisplayCardOptions.md) | Options to set card ID, styling options for each card detail, and callbacks |

#### Returns

[`DisplayCardTask`](DisplayCardTask.md)

**`Example`**

```ts
const chnStyle = {
  fontSize: '30px',
  fontColor: '#000000',
};
const panStyle = {
  fontSize: '30px',
  fontColor: '#000000',
};
const expStyle = {
  fontSize: '24px',
  fontColor: '#000000',
};
const cvvStyle = {
  fontSize: '24px',
  fontColor: '#000000',
};

const copyBtnStyle = {
  iconType: 'outlined',
  iconColor: 'black',
  iconSize: '24px',
  backgroundColor: 'rgba(255, 255, 255, 0)',
  backgroundHoverColor: 'rgba(255, 255, 255, 0.1)',
  padding: {
    top: '4px',
    bottom: '4px',
    left: '4px',
    right: '4px',
  },
  margin: {
    left: '8px',
  },
};

const displayCardTask = d1WebSdkClient.createDisplayCardTask({
  cardId: 'YOUR_CARD_ID',
  cardHolderViewOptions: {
    styles: chnStyle,
    maskCharacter: '*',
  },
  panViewOptions: {
    styles: panStyle,
    maskCharacter: '*',
    separator: ' ',
    allowCopyToClipboard: true,
    copyButtonProperties: copyBtnStyle,
  },
  expViewOptions: {
    styles: expStyle,
    maskCharacter: '*',
    format: 'MM/YY' | 'YY/MM' | 'MM/YYYY',
    allowCopyToClipboard: true,
    copyButtonProperties: copyBtnStyle,
  },
  cvvViewOptions: {
    styles: cvvStyle,
    maskCharacter: '*',
    allowCopyToClipboard: true,
    copyButtonProperties: copyBtnStyle,
  },
  eventCallbacks: {
    onStateChange(state) {
      // recommend this section for tracking user journey
      if (state === OP_FETCH_METADATA_START) {
        // starts animation
      }
      if (state === OP_FETCH_METADATA_STOP) {
        // stops animation
      }
      if (state === OP_DISPLAY_CARD_START)
        if (state === OP_DISPLAY_CARD_STOP) {
          // starts animation
          // stops animation
        }
    },
    onCopyToClipboard(field: 'PAN' | 'CVV' | 'EXP' | 'CHN') {
      // get notified which card detail is being copied to clipboard
    },
  },
});

// Now you will have access to additional display card methods.
await displayCardTask.displayCardMetadata();
await displayCardTask.displayCardDetails();
await displayCardTask.maskCardDetails();
```

---

### getSdkVersion

▸ **getSdkVersion**(): `string`

#### Returns

`string`

The current version of web SDK (for example, 1.0.0).

**`Example`**

```ts
d1WebSdkClient.getSdkVersion();
```

---

### login

▸ **login**(`issuerToken`): `Promise`\<`void`\>

This method authenticates the D1 back-end server with an issuer token.

#### Parameters

| Name          | Type     |
| :------------ | :------- |
| `issuerToken` | `string` |

#### Returns

`Promise`\<`void`\>

**`Example`**

```ts
const issuerToken = 'YOUR_ISSUER_TOKEN';

await d1WebSdkClient.login(issuerToken);
```

---

### logout

▸ **logout**(): `Promise`\<`void`\>

This method logs the end user out of the SDK and removes all the rendered views.

#### Returns

`Promise`\<`void`\>

**`Example`**

```ts
await d1WebSdkClient.logout();
```

---

### removeChangePinTask

▸ **removeChangePinTask**(): `Promise`\<`void`\>

This method removes the change PIN UI and ChangePinTask singleton object.

#### Returns

`Promise`\<`void`\>

**`Example`**

```ts
await d1WebSdkClient.removeChangePinTask();
```

---

### removeDisplayCardTask

▸ **removeDisplayCardTask**(): `Promise`\<`void`\>

This method removes the display card UI and DisplayCardTask singleton object.

#### Returns

`Promise`\<`void`\>

**`Example`**

```ts
await d1WebSdkClient.removeDisplayCardTask();
```
