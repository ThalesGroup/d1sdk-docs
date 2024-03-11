[d1-websdk](../README.md) / ViewOptions

# Interface: ViewOptions

## Hierarchy

- **`ViewOptions`**

  ↳ [`PanViewOptions`](PanViewOptions.md)

  ↳ [`ExpViewOptions`](ExpViewOptions.md)

## Table of contents

### Properties

- [allowCopyToClipboard](ViewOptions.md#allowcopytoclipboard)
- [copyButtonProperties](ViewOptions.md#copybuttonproperties)
- [maskCharacter](ViewOptions.md#maskcharacter)
- [styles](ViewOptions.md#styles)

## Properties

### allowCopyToClipboard

• `Optional` **allowCopyToClipboard**: `boolean`

---

### copyButtonProperties

• `Optional` **copyButtonProperties**: [`CopyButtonCssProperties`](CopyButtonCssProperties.md)

---

### maskCharacter

• `Optional` **maskCharacter**: `string`

Defines how the card information will appear when it is masked.
This value of this field is limited to only one character.

For example, when the mask character `*` is given:
| Normal card CVV value | Masked card CVV value |
|-----------------------|-----------------------|
| 123 | \*\*\* |

---

### styles

• **styles**: [`DisplayCardCssProperties`](DisplayCardCssProperties.md)
