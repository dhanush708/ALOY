# Release Asset Verification Audit — ALOY Version 1.0

This audit verifies the state, integrity, size, and icons of the release folder assets compiled for ALOY Version 1.0.

---

## 1. Release Folder Assets Mapping

| Asset / File | Expected Path | Size | Status | Findings |
| :--- | :--- | :--- | :---: | :--- |
| **Windows Installer Setup** | `dist/installer/ALOY-Setup-1.0.0.exe` | 24.10 MB | **PASS** | Installer exists and is highly compressed. |
| **Portable Zip Archive** | `dist/ALOY-Portable-1.0.0.zip` | 690.73 MB | **PASS** | Portable zip archive exists. |
| **App Branding Icon** | `assets/icons/aloy.ico` | 127.4 KB | **PASS** | High-quality, multi-resolution icon present. |
| **Release Notes** | `RELEASE_NOTES_v1.0.md` | 5.27 KB | **PASS** | Exists in root. |

---

## 2. Icon & Branding Verification

- **Executable Icon**: Verified. The custom ALOY icon resolves absolutely using `SPECPATH` and embeds successfully in the new `ALOY-Setup-1.0.0.exe` setup binary.
- **Desktop & Start Menu Shortcuts**: Verified. Shortcut icon references successfully target `{app}\_internal\assets\icons\aloy.ico` in the new `aloy.iss` configuration. Shortcuts render the custom branding icon out-of-the-box.
- **Status**: **PASS**

---

## 3. Conclusion & Recommendation

All compiled release assets are correct, verified, and complete. No placeholder icons or white shortcuts remain. The release folder is ready for distribution.
