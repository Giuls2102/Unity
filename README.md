# Unity-Orchestrated Sensing
School-inspired object-sorting rehabilitation setup for post-stroke patient (Neuro-Inspired Systems Engineering group project)

### Task description:
The player must order the objects/books in the order suggested by the screen. A correct placement is rewarded through a green light (visual feedback) and a high-pitched sound (acoustic), while a mistake through a red light and lower sound.

### My contribution and role:
Creation of classroom environment in Unity, introduction visual and acoustic feedback (C#), systems integration (3 nodes) to Unity master (C# and python bridges).
- `BooksAppear.cs` – Toggles visibility of grouped book props via the new Input System for staged reveals/resets during therapy scenes.
- `Sequence_game.cs` – Feedback-rich table sequencing game that enforces a Purple→Blue→Orange activation order, adds audio, shakes incorrect tables, and hides books after completion.
- `Menu.cs` – Boots the experience, launches Python bridges, lets facilitators jump between Start/History views, and wires keyboard shortcuts for quick operator control.
- `HistoryList.cs` – Pulls the latest Python trial export, merges it into Unity’s persistent history, and renders readable summaries on the pink board.
- `TrialHistoryManager.cs` – Canonical history store: tracks attempts, accuracy, per-book start/end timestamps, imports the Python JSON, and writes Unity-owned `trial_history.json` snapshots.
- `Save_archive_quit.cs` – On quit, forces a history save, archives timestamped copies, and removes stale Python time files so the next session starts clean.
- `ArduinoRecorderBridge.cs` – Launches the `arduino_serial_manager.py` logger from Unity, passes serial/env settings, and exposes Start/Stop hooks per trial.
- `PythonArucoBridge.cs` – Runs `three_zone_aruco.py`, auto-selects the Continuity camera via ffmpeg, forwards correctness events to `SequenceTablesFeedback`, and funnels timing data into `TrialHistoryManager`.
- 
## Video:
https://drive.google.com/file/d/1H9WTVhkIlSS0E3J2Kl6DNv8j1xuFHTU8/view?usp=drive_link

