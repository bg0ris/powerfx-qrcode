# Power Fx QR code generator

A Power Fx user-defined function that generates a QR code in Canvas Apps.
No PCF, no connectors, no external APIs. Just Power Fx.

## Usage

1. Paste the contents of `QrCode.fx` into **App → Formulas**.
2. Set the **Image** property of an Image control to:

```powerfx
QrCode(txt_Value.Text)
```

The function returns an SVG that renders directly in the Image control.

## Tips

- Validate your input before generating:

```powerfx
Len(txt_Value.Text) <= 106 && IsMatch(txt_Value.Text, "^[ -~]*$")
```

## Limitations

- Max **106 characters**.
- Printable ASCII only (no accents, emoji or line breaks). Other characters don't give an error, the QR code just comes out wrong.
