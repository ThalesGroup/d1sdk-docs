[d1-websdk](../README.md) / ExpViewOptions

# Interface: ExpViewOptions

## Hierarchy

- [`ViewOptions`](ViewOptions.md)

  ↳ **`ExpViewOptions`**

## Table of contents

### Properties

- [allowCopyToClipboard](ExpViewOptions.md#allowcopytoclipboard)
- [copyButtonProperties](ExpViewOptions.md#copybuttonproperties)
- [format](ExpViewOptions.md#format)
- [maskCharacter](ExpViewOptions.md#maskcharacter)
- [styles](ExpViewOptions.md#styles)

## Properties

### allowCopyToClipboard

• `Optional` **allowCopyToClipboard**: `boolean`

#### Inherited from

[ViewOptions](ViewOptions.md).[allowCopyToClipboard](ViewOptions.md#allowcopytoclipboard)

---

### copyButtonProperties

• `Optional` **copyButtonProperties**: [`CopyButtonCssProperties`](CopyButtonCssProperties.md)

#### Inherited from

[ViewOptions](ViewOptions.md).[copyButtonProperties](ViewOptions.md#copybuttonproperties)

---

### format

• `Optional` **format**: [`DateFormat`](../README.md#dateformat)

---

### maskCharacter

• `Optional` **maskCharacter**: `string`

Defines how the card information will appear when it is masked.
This value of this field is limited to only one character.

For example, when the mask character `*` is given:
| Normal card CVV value | Masked card CVV value |
|-----------------------|-----------------------|
| 123 | \*\*\* |

#### Inherited from

[ViewOptions](ViewOptions.md).[maskCharacter](ViewOptions.md#maskcharacter)

---

### styles

• **styles**: [`DisplayCardCssProperties`](DisplayCardCssProperties.md)

#### Inherited from

[ViewOptions](ViewOptions.md).[styles](ViewOptions.md#styles)
