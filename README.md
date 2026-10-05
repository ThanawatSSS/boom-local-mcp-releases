# Boom Local MCP — user guide

Boom lets ChatGPT work on your Windows PC: files, apps, the screen, browsers, Office and code, from the chat on your computer or your phone. Safety lives in Boom itself: anything with a real effect (deleting files, pushing to Git, closing a window) waits for your approval first.

> Full guide in Thai: [README_TH.md](README_TH.md) · What comes next: [ROADMAP.md](ROADMAP.md)

## 1. Install (Windows 10/11)

1. Download `BoomSetup-<version>-r<N>.exe` from [the latest release](https://github.com/ThanawatSSS/boom-local-mcp-releases/releases/latest).
2. Open it.
   - The installer is not code-signed yet, so Windows may show "Windows protected your PC". Select **More info**, then **Run anyway**.
   - Boom installs for your Windows account only. It does not need administrator rights.
3. Boom Control opens and a **B** icon appears in the system tray.

Boom starts with Windows and offers new versions on its **Updates** page. It updates only when you press the button.

## 2. Connect to ChatGPT (once)

Boom talks to ChatGPT through your own OpenAI Secure MCP Tunnel (no open ports, no public server). Boom Control's "Connect this PC" page walks you through it:

1. Create a tunnel in the OpenAI Platform and copy its `tunnel_id`.
2. Create an API key in the same account (permission Tunnels: Use). Boom keeps it on this PC only.
3. Enter both in Boom Control and press **Connect**.
4. In ChatGPT: Settings → Security and login → turn on **Developer mode** → Plugins → **+** → Connection **Tunnel** → choose your tunnel → name it "Boom".

Open a new chat and type `check Boom health`. After every Boom update, refresh the "Boom" plugin in ChatGPT and open a new chat.

## 3. Use it: say what you want

| You want to | Try | What happens |
|---|---|---|
| See the screen | `Show me my screen` | A screenshot in the chat |
| Type in an app | `Open Notepad and type "Hello from Boom", don't save` | Boom's bar appears; Boom checks the text landed |
| Use any app | `Open Paint and draw a small house with a roof, a door and windows` | The task card shows the steps and the latest picture |
| Browser | `Play any song in the YouTube Music tab in Brave` | Boom finds the tab directly |
| Files | `Create notes.txt in Documents saying "meeting Monday"` | A file in an allowed folder |
| Delete | `Delete report-old.txt in Documents` | An approval card, then the Recycle Bin (restorable) |
| Delete by rule | `Delete the .tmp files in Downloads older than Oct 1 except keep.tmp` | GPT restates the rule; one card shows the count, folders and the full list |
| Excel | `Open budget.xlsx in Documents and total column C` | Reads and writes the sheet without the mouse |
| Code / Git | `Run git status in my-app and summarize the changes` | A summary; pushing needs approval |
| This PC | `When did my PC last sleep, and for how long?` | From the Windows event log |

Tips: say the result you want and let GPT choose how. Add `send a screenshot of the result` to see the outcome. On iPhone, ChatGPT may show the task card only when the work is done; Boom Control's **Tasks** page shows it live.

## 4. Approvals

- Consequential actions show an **approval card** in the chat and in Boom Control on the PC; decide in either place, once.
- Can't see the card on your phone? Type `I can't see the approval card` and GPT shows the same card again.
- Several requests: the card says how many more wait; decide this one and press **Next request**.
- While approvals wait, the Boom tray icon shows a red number and blinks when a new one arrives.

## 5. While Boom uses the screen

Grey bar: Boom is only looking. Orange with a big 3 · 2 · 1 in the middle: Boom is about to use the mouse (only when you are using the PC). Blue: Boom is using mouse and keyboard; your clicks are held so they don't collide. Grey "waiting for the next step": use the PC freely. Hold **Esc** for one second to take control back at once.

## 6. Deleting and restoring

Ordinary deletes go to the Recycle Bin and the card offers **Restore** for exactly that delete (never over a file that now has the same name). Permanent deletion happens only when you ask for it. Where Windows would delete permanently without asking (network or removable drives, items larger than the bin), Boom refuses instead.

## 7. Other AI apps

Boom works with **ChatGPT** today. Claude (Desktop/Code), Gemini/Antigravity, Grok and local LLMs are planned; this guide will list how to connect each one when it is ready.

## 8. Help

Boom Control → **Report a problem**: creates a diagnostics file and drafts an email to boomhothkub@gmail.com (Boom sends nothing by itself).

## 9. What comes next

See [ROADMAP.md](ROADMAP.md): what is being built now and the order after it.

## 10. Uninstall

Open Windows Settings → Apps → Installed apps → **Boom Local MCP** → Uninstall. You can choose to also delete your Boom data (connection, API key, history, settings).

## Release files

| File | Purpose |
| --- | --- |
| `BoomSetup-<version>-r<N>.exe` | Installer and updater: installs Boom, or updates an existing install in place |
| `boom-<version>-r<N>.zip` | The package that Boom Control downloads for in-app updates |
| `release.json`, `release.json.sig` | Version, build and package SHA-256, signed with Boom's release key (ECDSA P-256) |

Boom checks every download before using it:
- It applies nothing unless `release.json` is signed by Boom's release key and the package matches its size and SHA-256.
- Setup then verifies every file against the package manifest. If a new version does not start, Boom rolls back.

