# Age of Aether — Elven UI asset pack (v0.1)

Original vector interface assets for the Age of Aether Android/PC client. Source references: https://github.com/xulek/muonline (client) and the local modified MuMono project. These SVGs are **new source artwork**, not drop-in replacements for OZP/OZT/WebP. Rasterize with transparent backgrounds and verify sizes, color space, alpha and UI layout before integration.

## Asset mapping
| New asset | Target component / existing source | Purpose |
|---|---|---|
| assets/ui/frames/elven-panel.svg | Client.Main/Controls/UI/Game/Inventory/InventoryControl.cs; Character/CharacterInfoWindowControl.Ornate.cs | inventory, stats panel background |
| assets/ui/frames/elven-title.svg | Client.Main/Assets/Interface/Ornate/Frame/title.webp | title plate; render title as localized text |
| assets/ui/controls/elven-button.svg | Client.Main/Assets/Interface/Ornate/Controls/button_primary.webp | action button |
| assets/ui/controls/elven-slot.svg | Client.Main/Assets/Interface/Ornate/Controls/slot.webp | inventory/skill slot |
| assets/ui/hud/elven-joystick.svg | Client.Main/Controls/UI/Game/Hud/Classic/VirtualJoystickControl.cs; Interface/DH/mi_stick_bg.OZP | joystick base |
| assets/ui/hud/elven-skill-ring.svg | Client.Main/Controls/UI/Game/Hud/Classic/TouchActionButtonsControl.cs; Interface/DH/mi_skill_frame.OZP | skill frame |
| assets/ui/branding/age-of-aether-logo.svg | login/splash branding: locate exact current code and resources first | wordmark |

## Safe integration
1. Clone this repository into a separate assets workspace. Never copy SVG over .OZP or .webp paths directly.
2. Inspect the actual modified local client: it may differ from upstream. Find all texture references, dimensions, and theme registrations before editing.
3. Add a new theme identifier/configuration and texture mappings, preserve original themes and files. Rasterize SVG to exact required pixel sizes and encode using supported formats. Respect mobile texture memory budgets.
4. Keep UI hitboxes, item grid, drag/drop, touch controls, aspect ratios and keyboard navigation intact.
5. Build a new LAN test APK with incremented versionCode, same approved signing key, and separate output. Do not publish to stable without physical validation.
6. Bulk stat allocation must be server-authoritative, validated for available points and packet/rate limits; do not simulate repeated unbounded clicks or trust client values.

## Scope
Visual art is a starter design system, not a complete audited replacement of every UI texture. No binary assets in the upstream client have been overwritten. Use this mapping as the starting point for a full local audit and migration manifest.
