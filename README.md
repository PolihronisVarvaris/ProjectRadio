# 🎧 Radio App – LUNA

## 📌 Project Overview
The idea for this project originated from our shared interest in radio broadcasting. Since all team members are involved in radio in one way or another, we decided to develop an electronic application that aligns with our passion. After several meetings and individual research, we confirmed that radio remains a popular and engaging topic, leading us to the creation of **LUNA Radio App**.

---

## 🎨 UI & Design Philosophy
The user interface was designed with harmony, clarity, and emotional tone in mind. We used a dark-themed background with highlights of **blue**, **white**, **pink**, and **red**. This color palette was chosen carefully to:
- Emphasize contrast (foreground vs. background).
- Support color psychology principles.
- Create a calming and engaging user experience.
- Ensure text readability.

### Design Guidelines Followed:
- Conservative color usage.
- Limit of 4–7 colors across elements.
- Consistent color-coded messages (e.g., red = danger).
- Color aids to structure dense visual content.
- Tailored colors for our target audience.

---

## 🛠️ App Structure & Functionalities

### 🖼️ Welcome Screen
- Displays LUNA logo and station name.
- Color tones: blue, pink, white, red (dark dominant).
- Evokes a sense of underground music or concert vibe.

### 🏠 Main Menu
- Buttons: `SCHEDULE`, `MUSIC`, `BROADCAST`, `TOP TEN`, `CONTEST`, `DEDICATIONS`, `ADVERTISEMENTS`, and clickable `LOGO` (History view).
- Consistent color scheme with white text on dark background.

---

## 📁 Feature Breakdown

### 1. 📅 SCHEDULE
- Fields: `Producer`, `Genre`, `Broadcast`, `Time`.
- Buttons: `ADD DATA`, `UPDATE`, `DELETE`, `REFRESH`, `Back`.
- Table updates live based on DB content.
- Input validation: red dot for errors, success alert on correct entries.

### 2. 🎵 MUSIC
- Fields: `Song`, `Artist`, `Year`, `Genre`.
- Buttons: `Input`, `Reload`, `Back`.
- Auto-suggestion: prompts user if the song is in this week's **Top Ten**.
- Displays: chart position, peak position, weeks on chart.
- Reload restores original input state.

### 3. 📻 BROADCAST
- Dropdown: Select `Producer`.
- Shows relevant `SHOWS` table and `Average Profit`.
- Empty selection resets display.

### 4. 🔟 TOP TEN
- Table Columns: `This Week`, `Title`, `Artist`, `Award`, `Peak`, `Weeks`.
- Dropdown: Filter by `Artist` to see awards, #songs, chart history.
- Button: `Song of the Year` reveals special winner.

### 5. 🏆 CONTEST
- Button: `Generate` randomly displays winner’s `ID` and `Name`.

### 6. 💌 DEDICATIONS
- Fields: `ID`, `Name`, `Song Title`, `Reason`.
- Adds user entry and joins contest.
- Check button: shows how many users dedicated the same song and why.

### 7. 📢 ADVERTISEMENTS
- Text area for SQL query display.
- Features:
  - `Check most profitable producer`
  - `Check most profitable product`
  - Enter `Broadcast Name` to view related sponsors.

### 8. 📜 HISTORY (LOGO)
- Clicking the LUNA logo opens a log table of all user operations:
  - `Operation`, `Date`, `Producer`, `Genre`, `Broadcast`, `Time`, `UserID`, `Table`, `CompetitionID`, `LuckyID`.

---

## 📊 Database & ER Model

### Key Tables & Relationships
- `MUSIC`: `title` (PK), connected to `TOP_TEN`, `DEDICATION`.
- `TOP_TEN`: `this_week` (PK), `title` (FK), `artist`, `award`, `peak_position`, `weeks_on_chart`.
- `PROGRAM`: `broadcast` (PK), `genre` (FK), `producer`, `time` (unique).
- `ADS`: `company` (PK), `product`, `cost`, `broadcast` (FK).
- `DEDICATION`: `id` (PK), `name`, `reason`, `title` (FK).
- `COMPETITION`: `lucky` (PK), `id` (FK from `DEDICATION`).
- `LOG_FILE`: Logs all user activities and changes.

### Relationships
- One-to-one or one-to-many between MUSIC, PROGRAM, ADS, DEDICATION, COMPETITION.
- Consistency enforced using primary and foreign keys.

---

## ⚙️ Stored Procedures (10 Total)

### Common Procedures (Across All Frames)
1. **Insert Data**
2. **Delete Data**
3. **Update Data**
4. **Refresh Tables**
5. **Dynamic Queries & UI Integration**

### Special Procedures

1. **FIRST_PROCEDURE_BROADCAST**  
   - `IN`: Producer name  
   - `OUT`: Table of broadcasts by producer  

2. **TWO_PART_A_LUCKY / TWO_PART_B_RANDOM**  
   - No input required  
   - Picks a random winner (`pointer`) from `lucky` entries  
   - Outputs: `Pointer`, `User ID`, `Name`  

3. **THIRD_SONG_TOP_TEN**  
   - `IN`: Song title  
   - Returns: Rank info, chart stats

*(List continues as needed – include more if required)*

---

## 👨‍💻 Tech Stack
- **Java** (Swing – `JFrame Forms`)
- **MySQL** – Relational database
- **SQL Procedures** – Backend logic
- **JDBC** – Java-Database connectivity

---

## 📚 Conclusion
This project merges our shared passion for radio with a structured software solution, featuring a visually engaging interface, robust database integration, and interactivity. We believe LUNA offers users an immersive radio-themed experience with dynamic content and real-time engagement.

---

## ✨ Team
> Created by passionate radio lovers and developers  
> 🎓 Final project for [University / Course Name]

Let me know if you'd like the same README translated into Greek, or if you need screenshots, logos, or a project structure to include!


