# Asset Specification Guide

Guidelines for creating and maintaining assets for `app-*` modules within the `somosuno-assets` repository.

## Required Files per Application

Every application folder (`app-*`) must contain the following set of assets.

| File Name | Dimensions | Format | Notes |
| :--- | :--- | :--- | :--- |
| `logo.png` | 200x200 px | PNG (Alpha) | Main application logo. |
| `logo-dark.png` | 100x100 px | PNG (Alpha) | Inverted/dark mode version of the logo. |
| `naming.png` | 150x100 px | PNG (Alpha) | Application name in stylized typography. |
| `naming-dark.png` | 150x100 px | PNG (Alpha) | Inverted/dark mode version of the naming. |
| `email.png` | 400x140 px | PNG/JPG | Header banner for email communications. |
| `favicon.ico` | Multi-size | ICO | Includes 16, 24, 32, 48, and 64 px versions. |

## Technical Requirements

### Transparency (Alpha Channel)
- `logo.png`, `logo-dark.png`, `naming.png`, and `naming-dark.png` **must** have a transparent background to blend with the application header.
- `favicon.ico` should also support transparency.

### Naming Typography
- The `naming.png` files must be legible within the 150x100 space.
- If the name is long, use two lines of text to ensure legibility and prevent clipping.

### Dark Mode
- Files suffixed with `-dark` are used when the application is in Dark Theme. These should generally be white or high-contrast versions of the primary assets.

## Validation & Processing Tools

We use **ImageMagick** for asset validation and conversion.

### Example: Checking Favicon Sizes
```powershell
& "C:\Program Files\ImageMagick-7.1.2-Q16-HDRI\magick.exe" identify "C:\repos_dmr\somosuno-assets\app-tattoo\favicon.ico"
```

### Example: Creating a Favicon from PNG
```powershell
& "C:\Program Files\ImageMagick-7.1.2-Q16-HDRI\magick.exe" convert logo.png -define icon:auto-resize=16,24,32,48,64 favicon.ico
```