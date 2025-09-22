# Update to v3.4.0!
**This is a test** of the *update available* notification. This message appears because the manifest's `latest_version` is higher than your installed version.

### Added
- **New Patchouli Guide Book**
    -   Replaced the original vanilla written book with a comprehensive, feature-rich guide book powered by the Patchouli library.
    -   Features a completely custom user interface, including a unique book texture and a custom-coded landing page layout with a wrapped, multi-line subtitle for a more polished presentation than what Patchouli offers by default.
    -   Implemented a dynamic text wrapping and pagination system for entry titles, ensuring that long or translated titles do not render off the edge of the page.
    -   Includes a robust backwards-compatibility system that automatically detects and upgrades any old guide books found in a player's inventory or any opened container to the new Patchouli version.

### Changed
- **Optimized Language File Generation**
    -   Refactored the data generation process for the `en_us.json` language file to eliminate the creation of redundant, prefixed translation keys for the configuration screen.
    -   This results in a smaller, cleaner, and more efficient language file with no impact on in-game text. Easier translating!

### Fixed
- **Resolved Server Crash on Hamster Throw**
    -   Fixed a `NullPointerException` that would crash dedicated servers when a player used the "Throw Hamster" keybind.
    -   The crash was caused by server-to-client sound packets being registered only on the client, leading to an error when the server attempted to send them.
    -   All network packet registrations have been consolidated into a single, common method, ensuring both the server and client are aware of all packet types.
- **Corrected Configuration Synchronization**
    -   Replaced the incorrect `@ClientModifiable` annotation with the appropriate `@NonSync` annotation for all client-side settings in the configuration file.
    -   This change prevents a potential issue where clients could modify server-synced settings without permission and ensures that client-only settings (like UI and animation options) are handled correctly.


This involves changes to the `HamsterEntity` class.

---
[View the full changelog on Modrinth](https://modrinth.com/mod/adorable-hamster-pets/versions)