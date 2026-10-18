# Forgewright

Forgewright is a personal build of [Forge](https://github.com/Card-Forge/forge), the open-source Magic: The Gathering
rules engine, with [Deckwright](https://chriswatkins2316.github.io/Deckwright/) built in. It is not the official Forge
and is not affiliated with the Forge team or with Wizards of the Coast. All credit for the game itself goes to the Forge
developers. Like Forge, it is free software under the GNU General Public License v3 (see LICENSE).

What's different from Forge:

- A **Deckwright** button on the home screen opens the Deckwright app inside Forgewright.
- Decks sent from Deckwright ("Play it in Forge") go straight into Forgewright's Deck Manager.
- It installs as its own app (`forge.app.forgewright`), next to the official Forge.

How it's kept: this repository stays identical to Forge apart from three added files, so "Sync fork" never conflicts.
All of the Forgewright changes live in `forgewright.patch`, which the build applies on top of Forge's code. It touches
`forge-gui-android/src/forge/app/DeckwrightActivity.java` (new), `forge-gui-android/src/forge/app/Main.java`,
`forge-gui-android/src/main/AndroidManifest.xml`, `forge-gui-android/pom.xml` (the `android-dev-build` profile),
`forge-gui-android/proguard.cfg`, `forge-gui-mobile/src/forge/screens/home/HomeScreen.java` and
`forge-gui/src/main/java/forge/interfaces/IDeviceAdapter.java`. The build itself is `.github/workflows/forgewright-android.yml`.

To build: Actions tab, **Build Forgewright for Android**, Run workflow. The app appears under Releases.
To pick up Forge's latest changes: on the repository page tap **Sync fork**, then run the build again.
