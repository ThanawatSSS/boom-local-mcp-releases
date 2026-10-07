# Boom Local MCP — user guide

Boom lets ChatGPT work on your Windows PC: files, apps, the screen, browsers, Office and code, from the chat on your computer or your phone. Safety lives in Boom itself: anything with a real effect (deleting files, pushing to Git, closing a window) waits for your approval first.

> Full guide in Thai: [README_TH.md](README_TH.md) · What comes next: [ROADMAP.md](ROADMAP.md)

## 1. Install (Windows 10/11)

1. Download `BoomSetup-<version>-r<N>.exe` from [the latest release](https://github.com/ThanawatSSS/boom-local-mcp-releases/releases/latest).
2. Open it.
   - The installer is not code-signed yet, so Windows may show "Windows protected your PC". Select **More info**, then **Run anyway**.
   - Boom installs for your Windows account only. It does not need administrator rights.
3. Boom Control opens and a **B** icon appears in the system tray.

Boom starts with Windows and offers new versions on its **Updates** page. It updates only when you press the button. If it says work is still open, the overview shows what (for example a browser Boom opened for an AI) with a button to close it; Boom also closes such a browser after 15 minutes unused. If a version before r46 still cannot update after that, restart Boom (close and reopen Boom Control, or restart the PC) and try again.

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
| Files | `Create notes.txt in Documents saying "meeting Monday"` | A file where you said |
| Your apps' MCP | `Add the Blender MCP that Claude Code has to Boom` | Boom imports it, checks for conflicts, and every AI app on Boom can use it |
| Delete | `Delete report-old.txt in Documents` | An approval card, then the Recycle Bin (restorable) |
| Delete by rule | `Delete the .tmp files in Downloads older than Oct 1 except keep.tmp` | GPT restates the rule; one card shows the count, folders and the full list |
| Excel | `Open budget.xlsx in Documents and total column C` | Reads and writes the sheet without the mouse |
| Code / Git | `Run git status in my-app and summarize the changes` | A summary; pushing needs approval |
| This PC | `When did my PC last sleep, and for how long?` | From the Windows event log |
| 3D | `Make a solid-wood dining chair in SketchUp, buildable so I can make it for real; save it as Documents\boom-3d\chair.skp` | GPT asks what is still open, works in a craftsperson's stages, checks every side and hands over with a cut list |

Tips: say the result you want and let GPT choose how. Add `send a screenshot of the result` to see the outcome. On iPhone, ChatGPT may show the task card only when the work is done; Boom Control's **Tasks** page shows it live.

## 4. Approvals

- Consequential actions show an **approval card** in the chat and in Boom Control on the PC; decide in either place, once.
- Can't see the card on your phone? Type `I can't see the approval card` and GPT shows the same card again.
- Several requests: the card says how many more wait; decide this one and press **Next request**.
- While approvals wait, the Boom tray icon shows a red number and blinks when a new one arrives.

## 5. While Boom uses the screen

Grey bar: Boom is only looking. Orange with a big 3 · 2 · 1 in the middle: Boom is about to use the mouse (only when you are using the PC). Blue: Boom is using mouse and keyboard; your clicks are held so they don't collide. Grey "waiting for the next step": use the PC freely. Hold **Esc** for one second to take control back at once.

Screen work is lighter and lands where it should: after each action the AI gets only the controls that changed, clicks work on drawing canvases (Paint), and the AI can search a window for a control by name. Drawing in Paint has its own know-how (`open Paint and draw a house with a sun`).

## 6. Deleting and restoring

Ordinary deletes go to the Recycle Bin and the card offers **Restore** for exactly that delete (never over a file that now has the same name). Permanent deletion happens only when you ask for it. Where Windows would delete permanently without asking (network or removable drives, items larger than the bin), Boom refuses instead.

## 7. 3D work and craft know-how

Boom gives every AI the same **craft know-how**, so results are things you can use, not boxes stuck together:
- **Knowledge from validated occupational standards** (Thailand's TPQI, the EU's ESCO) per kind of work: perspective and thinking in 3D, 3D modelling, characters (games, animation), architecture, construction, product design, joints and assembly, and clean, light models. Chinese timber halls follow the Song building standard 营造法式 and measured surveys: the frame on every slope, bracket sets at every corner, the roof curve computed by its rule, doors on their pivots.
- **Checked at the start of every task.** 3D is the first kind of work with know-how, and more kinds will follow. For work it does not cover yet, GPT simply goes on.
- **Detailed is the standard level.** If you do not say, GPT models in detail, to your reference picture when you give one, and tells you so in one line.
  - **Want it quick?** Say so in the chat: `mock-up`, `rough`, `quick`, `ร่างคร่าวๆ`, `ทำเร็วๆ` gives a mock-up (shape and proportion only).
  - **Want to make it for real?** Say `buildable` (`ละเอียดพิเศษ`, `ทำได้จริง`, `ถอดชิ้น`): every part separate with its joints.
  - You can change the level at any time in the chat.
- **Asks only what you have not said clearly:** which file to work in (a new one, the open one, or a named one), and how it will be made when it is buildable. What you said clearly is not asked again. Boom makes sure of it: the work does not start, and SketchUp or Blender does not open, until your own answer settles each question. You can also say "up to you", or drop the work.
- **Buildable models:** every part is a separate piece with its joints (tenons and mortises, corner blocks, screws with pilot holes), with exploded and per-part pictures and a cut list taken from the model.
- **Boom checks SketchUp models itself:** on a copy, in its own SketchUp window for about half a minute. It finds parts that overlap (a missing hole), parts that touch nothing, fasteners that hold nothing, and takes the cut list from the model. Buildable work is not marked done until Boom's check of the final file is clean.
- **Each object is one group,** and repeated parts share one definition.
- **From a plan or a layout picture:** give a PDF floor plan or a picture of a layout (`build this office layout from D:\plans\level2.pdf`). Boom shows it to GPT, GPT finds its scale from a written dimension and checks it on a second one, lays the plan under the model at real size, builds on it and checks the top view against it.
- **In your own model:** edit or update an object, or `make a new chair in place of the object named Chair 3`. The new one stands where the old one stood, turned the same way; the old one is hidden on the tag "Replaced by Boom", not deleted, and one Undo takes the change back.
- **Clicking in the AI's SketchUp window is fine:** look around or click while it works; GPT carries on in the same file instead of opening it again.
- **The checks and what you asked for are on the task card:** the know-how the work follows, the checks it must pass (for example the load path of a chair, or comparing with your reference picture), and each thing you asked for with GPT's answer. The work is not marked done while one is open.
- **Light enough for an ordinary PC:** Boom's SketchUp check also reports how heavy the model is (faces, triangles, textures, shadows) and slivers left by cuts; GPT keeps detail where it is seen and repeats as one definition.
- **Buildings are counted:** the columns, purlins and rafters in the finished model must match the plan on every side, hip ends and corners included.
- **Your brief decides:** a building you name is modelled as surveyed; when the brief leaves the choice, the AI says which building and period it chose and what that means for the look. Doors are shown partly open, so you see which side turns and which way.
- **Boom checks 3D web pages itself:** one call shows the page from every side and in X-ray, counts its parts by type with their positions, and measures what it costs while you are not touching it, in your own Chrome on the graphics card.
- **Light by design:** web pages are built to choose a light mode on weak devices (`?q=low` forces it), and the hand-over reports draw calls and the idle cost measured on the finished page.
- Every stage has a checkpoint, and a hand-over note says what was made, the standards used, what was checked and how to rebuild it.

Software:
- **Blender** (characters, organic forms, objects): needs Blender 4.2 or later. Boom looks at a .blend from every side (top, bottom, left, right, front, back, iso and eye level) with sizes in metres, with the file's scripts disabled and without saving over it.
- **SketchUp** (houses, buildings, furniture): built into Boom's MCP hub (section 8). With the *MCP Server for SketchUp* extension installed, Boom opens SketchUp with its MCP on, with no clicks, and GPT builds with scripts whose errors come back with the exact line, using Boom's tested helpers. The Ruby Console is never needed. GPT picks SketchUp's own tool that fits each part (Push/Pull, Follow Me, Intersect, Solid Tools); Solid Tools, for solid parts that join, need SketchUp Pro.
- With a Blender MCP add-on in Boom (section 8), Boom opens Blender with it started too.
- **A web page (Three.js):** one HTML file that opens from disk. It draws only when something changes, so it costs nothing while you are not touching it, and GPT checks it from every side with Chrome on your graphics card.
- **Where files go:** say it in your request (`save it in D:\3D_models\chairs`); if you don't, GPT asks. There is no list of folders to set up. Boom never touches Windows, installed programs, apps' settings and sign-ins, its own data or secret files.
- **Your apps can be anywhere.** Boom finds them on your PC, including other drives, and remembers where each app was opened from. If an app is somewhere Boom cannot find (a portable copy, for example), tell GPT its full path once.

**Following the work:** the task card shows what Boom itself saw last (for example "writing build.rb", "opening SketchUp"), and "ChatGPT is thinking or writing" (or the name of the AI app doing the work) when no command has come for a while, so you can tell where the work is even when the AI reports its steps late.

Add your own know-how: put folders with a `SKILL.md` in `%LOCALAPPDATA%\BoomLocalMCP\knowhow`. Boom reads them as text only, never runs scripts that come with them, and know-how can never skip an approval.

## 8. Your apps' MCP (MCP Hub)

Many apps have their own MCP, a way for an AI to use them directly. Add an app's MCP to Boom once and every AI app connected to Boom can use it, with no setup in each one.
- **SketchUp is built in** (it needs the *MCP Server for SketchUp* extension in SketchUp).
- **Already set up in Claude Code, Claude Desktop or Codex?** Boom Control → **MCP ของแอป** lists them: press **Import**. Or ask GPT: `Add the blender MCP from Claude Code to Boom`.
- **A new one:** ask GPT to add it from its setup instructions, or add it in Boom Control.
- **Boom checks for conflicts every time:** one that is already there (GPT asks whether to replace it), two apps on the same port, or anything that would break Boom (refused). For other conflicts you choose: change the settings, or add it anyway with the warning kept.
- When an app's MCP needs the app open, Boom opens it. Calls need no approval card; each one is recorded and shown on the task card.
- Keys and tokens are stored encrypted; GPT sees only their names.

## 9. Other AI apps

- **ChatGPT** and **Codex** (desktop) connect through the Boom plugin (section 2). Codex uses its own tools first and Boom for know-how, your apps' MCP and approvals.
- **Claude Desktop, Claude Code, WorkBuddy, Antigravity, Cline and Freebuff** connect on this PC:
  1. Open Boom Control → **แอป AI**.
  2. Press **เชื่อมต่อ** next to the app.
  3. Close and open that app once.

  Boom adds one entry, "boom", to the app's own MCP settings (a copy of the file is kept first). The app then starts Boom's connector, `boom-connect.exe`, which reaches the Boom already running on this PC.
  - **Same Boom for every app:** the same know-how, your apps' MCP, inspectors, task card and approvals. Every record says which app asked.
  - **Approvals:** these apps show no Boom card, so a request that needs your approval comes up in Boom Control with a notification. Decide there, then tell the AI.
  - **Disconnect** on the same page removes Boom's entry and stops that app's access.
  - **Freebuff** asks you to approve Boom's entry in Freebuff before it runs it.
- **Any other AI app:** Boom Control → **แอป AI** → **แอปอื่น**. Name it and press **สร้างการเชื่อมต่อ**: Boom shows the entry to copy into that app's MCP settings (its `mcpServers`), once. Restart the app. Each connection has its own key, its tasks show its name, and **ลบ** on the same page stops it.
- Grok and local LLMs are planned.

## 10. Help

Boom Control → **Report a problem**: creates a diagnostics file and drafts an email to boomhothkub@gmail.com (Boom sends nothing by itself).

## 11. What comes next

See [ROADMAP.md](ROADMAP.md): what is being built now and the order after it.

## 12. Uninstall

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

