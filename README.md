# Boom Local MCP releases

This repository holds only Boom's release files: the installer and the signed update files. Boom Control checks the latest release here to offer updates.

## Install (Windows 10/11)

1. Download `BoomSetup-<version>-r<N>.exe` from [the latest release](../../releases/latest).
2. Open it.
   - The installer is not code-signed yet, so Windows may show "Windows protected your PC". Select **More info**, then **Run anyway**.
   - Boom installs for your Windows account only. It does not need administrator rights.
3. When Boom Control opens, follow **เชื่อมต่อเครื่องนี้กับ ChatGPT** (connect this PC to ChatGPT). You need:
   - a Secure MCP Tunnel and a runtime API key from [OpenAI Platform](https://platform.openai.com/settings/organization/tunnels);
   - ChatGPT **Developer mode** turned on (Settings → Security and login).

## What each release contains

| File | Purpose |
| --- | --- |
| `BoomSetup-<version>-r<N>.exe` | Installer and updater: installs Boom, or updates an existing install in place |
| `boom-<version>-r<N>.zip` | The package that Boom Control downloads for in-app updates |
| `release.json`, `release.json.sig` | Version, build and package SHA-256, signed with Boom's release key (ECDSA P-256) |

Boom checks every download before using it:
- It applies nothing unless `release.json` is signed by Boom's release key and the package matches its size and SHA-256.
- Setup then verifies every file against the package manifest. If a new version does not start, Boom rolls back.

## Uninstall

Open Windows Settings → Apps → Installed apps → **Boom Local MCP** → Uninstall. You can choose to also delete your Boom data (connection, API key, history, settings).

---

**ภาษาไทย (Thai):**
- **ติดตั้ง:** ดาวน์โหลด BoomSetup จาก release ล่าสุดแล้วเปิดไฟล์ ถ้า Windows เตือน ให้กด More info → Run anyway จากนั้นทำตามหน้า "เชื่อมต่อเครื่องนี้กับ ChatGPT" ใน Boom Control
- **อัปเดต:** Boom Control เช็กรุ่นใหม่ให้วันละครั้ง และจะอัปเดตเมื่อคุณกดเท่านั้น
- **ถอนการติดตั้ง:** ทำได้จาก Windows Settings → Apps
