[d1-websdk](../README.md) / PanViewOptions

# Interface: PanViewOptions

## Hierarchy

- [`ViewOptions`](ViewOptions.md)

  ↳ **`PanViewOptions`**

## Table of contents

### Properties

- [allowCopyToClipboard](PanViewOptions.md#allowcopytoclipboard)
- [copyButtonProperties](PanViewOptions.md#copybuttonproperties)
- [maskCharacter](PanViewOptions.md#maskcharacter)
- [separator](PanViewOptions.md#separator)
- [styles](PanViewOptions.md#styles)

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

### separator

• `Optional` **separator**: `string`

Defines how the card PAN digits will be separated. If this is specified, the digits
will be divided into four blocks of four digits.
This value of this field can only contain at most two characters and cannot contain any numeric values.

For example, when an empty character separator `' '` is given:
| Normal card PAN value | Card PAN value with separator |
|-----------------------|-------------------------------|
| 1234567887654321 | 1234 5678 8765 4321 |

---

### styles

• **styles**: [`DisplayCardCssProperties`](DisplayCardCssProperties.md)

#### Inherited from

[ViewOptions](ViewOptions.md).[styles](ViewOptions.md#styles)
