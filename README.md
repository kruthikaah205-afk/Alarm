# ⏰ Smart Alarm Clock

A simple and user-friendly **Smart Alarm Clock web application** built with **Python and Streamlit**. The application allows users to set an alarm, select an alarm tone, configure snooze duration, and stop or snooze the alarm when it rings.

## 📌 Features

* 🕐 Displays the current system time.
* 🔔 Set an alarm using:

  * Hour
  * Minute
  * AM/PM
* 🎵 Choose from three alarm tones:

  * Classic Beep
  * Soft Chime
  * Rapid Alert
* 😴 Customize snooze duration from **1 to 60 minutes**.
* ❌ Cancel an alarm before it rings.
* 🚨 Automatically detects when the alarm time is reached.
* 🔊 Plays the selected alarm sound in the background.
* 😴 Snooze the alarm for the configured duration.
* 🛑 Stop the alarm completely.
* 🔄 Automatically refreshes the application every second while an alarm is active.
* 💻 Uses a Streamlit-based graphical interface.

## 🛠️ Technologies Used

* **Python**
* **Streamlit**
* **datetime** – Handles current time and alarm scheduling.
* **threading** – Runs the alarm sound in the background.
* **time** – Provides delays and refresh timing.
* **winsound** – Generates alarm sounds on Windows.

The application configures the Streamlit page with the title **"Smart Alarm Clock"** and a clock-themed icon.

## 📂 Project Structure

```text
Smart-Alarm-Clock/
│
├── alram(2).py
└── README.md
```

## ⚙️ Requirements

Make sure Python is installed on your computer.

Install Streamlit using:

```bash
pip install streamlit
```

> **Note:** The project uses Python's `winsound` module, so the alarm sound functionality is designed for **Windows**.

## 🚀 How to Run

### Step 1: Open the project folder

Open Command Prompt or PowerShell and navigate to your project directory:

```bash
cd path\to\Smart-Alarm-Clock
```

### Step 2: Install Streamlit

```bash
pip install streamlit
```

### Step 3: Run the application

```bash
streamlit run "alram(2).py"
```

Streamlit will open the application in your web browser.

## 🕐 How to Use

1. Open the Smart Alarm Clock application.
2. Check the current time displayed on the screen.
3. Select the desired **hour**.
4. Select the desired **minute**.
5. Select **AM** or **PM**.
6. Select an alarm tone.
7. Select the snooze duration.
8. Click **🔔 Set Alarm**.
9. The application displays the scheduled alarm time and alarm status.
10. When the scheduled time is reached, the alarm starts playing.
11. Choose:

    * **😴 Snooze** – postpones the alarm.
    * **🛑 Stop Alarm** – stops and cancels the alarm.

The application stores alarm information using Streamlit session state, including the alarm status, alarm time, selected tone, snooze duration, and alarm thread.

## 🎵 Alarm Tones

The application provides three built-in sound patterns:

| Tone         | Description                        |
| ------------ | ---------------------------------- |
| Classic Beep | Five repeated high-frequency beeps |
| Soft Chime   | Three slower, softer beeps         |
| Rapid Alert  | Multiple short alert beeps         |

The tones are implemented using the Windows `winsound.Beep()` function.

## 😴 Snooze Function

When the alarm is ringing, clicking **Snooze** creates a new alarm time by adding the configured snooze duration to the current time.

For example:

```text
Current time: 07:30 AM
Snooze: 5 minutes

New alarm: 07:35 AM
```

The application then resets the alarm-triggered state and resumes checking the new alarm time.

## 🔄 Automatic Alarm Checking

The application continuously checks the current time against the scheduled alarm time. When the current time reaches or passes the alarm time, the alarm is triggered and the selected sound is started in a background thread.

The application refreshes every second while an alarm is active:

```python
if st.session_state.alarm_set:
    time.sleep(1)
    st.rerun()
```

## 📅 Handling Passed Alarm Times

If the selected alarm time has already passed for the current day, the application automatically schedules the alarm for the **next day**.

For example:

```text
Current time: 10:00 PM
Selected alarm: 08:00 PM

Alarm scheduled for: 08:00 AM tomorrow
```

## 🎨 User Interface

The application uses custom CSS to create:

* Centered application title
* Large digital clock
* Styled alarm settings
* Alarm information box
* User-friendly buttons
* Status messages

The main interface displays the title **"⏰ Smart Alarm Clock"** and provides a simple description for setting alarms and using snooze.

## 🔮 Future Enhancements

Possible improvements include:

* 📅 Multiple alarms
* 🔁 Repeat alarms for specific days
* 🎶 Upload custom alarm sounds
* 🌙 Dark mode
* 🔐 User accounts
* 📱 Mobile-friendly interface
* ⏱️ Countdown timer
* 💤 Sleep timer
* 📊 Alarm history
* 🔔 Browser notifications
* 🌐 Cross-platform sound support
* 🗣️ Voice-controlled alarm setting

## ⚠️ Limitations

* The `winsound` module is Windows-specific.
* The application is designed to run while the Streamlit application remains active.
* Alarm settings are stored in Streamlit session state and are not persistent across application restarts.
* Only one active alarm is supported at a time.

## 👩‍💻 Author

**Kruthika AH**


