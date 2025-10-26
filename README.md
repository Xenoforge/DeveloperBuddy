# 🛠️ Developer Buddy

Unity Editor productivity tracking tool for monitoring development time, idle periods, and project statistics.

## 📋 Features

### Core Tracking
- **Session Management**: Automatic session tracking with start/end times
- **Idle Detection**: Smart idle time detection with activity monitoring
- **Playtest Tracking**: Automatic play mode duration recording
- **Data Persistence**: ScriptableObject-based data storage with caching

### Editor Window Tabs

#### 1. Overview
- Project metadata (name, start date, age)
- Total active work time
- Current session statistics
- Real-time idle tracking

#### 2. Reports
- Average session duration
- Daily/monthly work time analytics
- Last 7 days work graph
- Productivity pie chart (active vs idle)
- **Report Generation**: Create detailed project reports
- **Export Options**: Export to TXT, CSV, or JSON formats

#### 3. Progress (Roadmap)
- Category-based task management
- Point system for tasks
- Progress tracking with completion percentages
- Default roadmap templates

#### 4. Reminder
- Idle time alerts
- Long work session warnings
- Daily goal tracking
- Custom session end reminders

#### 5. Budget/Cost
- Hourly rate configuration
- Labor cost calculation
- Additional expenses tracking
- Multi-currency support (USD, EUR, GBP, JPY)

#### 6. Advisor
- Smart recommendations based on work patterns
- Session duration analysis
- Idle time warnings
- Work intensity monitoring
- Playtest balance suggestions
- Activity continuity tracking
- Productivity trend analysis
- Project phase guidance

## 🚀 Installation

1. Import package into your Unity project
2. Window → Developer Buddy to open the tool
3. Data auto-creates at `Assets/DeveloperBuddy/Data/ProjectData.asset`

## 📊 Data Structure

### SessionData
- Duration, start/end times
- Playtest count and duration
- Idle time and count
- Active work time calculation

### ProjectData
- Session history
- Roadmap categories and tasks
- Budget settings
- Reminder preferences
- Cached aggregate statistics

## ⚙️ Technical Details

### Performance Optimization
- **Caching System**: Aggregate stats cached for 5 seconds
- **Session Archiving**: Auto-archive when exceeding 1000 sessions
- **Lazy Recalculation**: Stats only update when marked dirty

### Idle Detection
Updates every second, monitors:
- Mouse/keyboard input
- Hierarchy changes
- Selection changes
- Play mode transitions
- Scene view activity

### Auto-Save
- Session data saves every 1 minute
- Automatic save on editor quit
- Safe save during compilation/play mode

## 📁 File Structure

```
Assets/DeveloperBuddy/
├── Data/
│   ├── ProjectData.asset
│   └── Archives/
├── Editor/
│   ├── Core/
│   │   ├── DeveloperBuddyWindow.cs
│   │   └── IDevBuddyTab.cs
│   ├── Tabs/
│   │   ├── OverviewTab.cs
│   │   ├── ReportsTab.cs
│   │   ├── ProgressTab.cs
│   │   ├── ReminderTab.cs
│   │   ├── BudgetTab.cs
│   │   └── AdvisorTab.cs
│   └── Tracking/
│       ├── ProjectTracker.cs
│       └── IdleTracker.cs
```

## 🔧 Configuration

### Idle Settings
- Default threshold: 60 seconds
- Customizable via ProjectData

### Archive Settings
- Warning threshold: 500 sessions
- Auto-archive threshold: 1000 sessions
- Archives saved to: `Data/Archives/`

### Cache Settings
- Default TTL: 5 seconds
- Auto-refresh on data changes

## 💡 Usage Tips

1. **First Time Setup**: Data creates automatically on first editor session
2. **Session Tracking**: Starts automatically when Unity opens
3. **Performance**: Enable archiving if session count grows large
4. **Roadmap**: Use default template or create custom categories
5. **Budget**: Set hourly rate for accurate cost tracking
6. **Advisor**: Check regularly for productivity insights
7. **Report Export**: Generate reports from Reports tab
   - **TXT**: Human-readable summary report
   - **CSV**: Spreadsheet-compatible session data
   - **JSON**: Complete data export for external tools

## 🎯 Advisor Recommendations

The Advisor tab provides real-time insights across 7 categories:

- **Session Duration**: Optimal 1-3 hour sessions
- **Idle Time**: Alerts when >30% idle
- **Work Intensity**: Daily workload balance
- **Playtest Balance**: 10-25% testing recommended
- **Activity Continuity**: Tracks work streaks
- **Productivity Trends**: Week-over-week comparison
- **Project Phase**: Stage-appropriate guidance

## 📈 Metrics Tracked

- Total development time
- Active work time (idle excluded)
- Session count and averages
- Playtest statistics
- Idle events and duration
- Labor costs
- Roadmap completion progress

## 🔒 Data Safety

- ScriptableObject persistence
- Automatic backup via archiving
- Safe concurrent operations
- Validation on load

## 🐛 Debug Mode

Enable with: `DEVBUDDY_DEBUG` in Scripting Define Symbols

Logs:
- Tracker initialization
- Session creation/updates
- Cache operations
- Archive operations

## 📤 Report Export

Generate and export project reports from the Reports tab.

### Export Formats

#### TXT Format (Summary Report)
Human-readable text report including:
- Project overview (name, start date, age)
- Work time statistics (total, active, idle)
- Session analytics (count, average duration)
- Playtest metrics
- Last 7 days breakdown
- Productivity analysis
- Roadmap progress (if enabled)
- Budget summary (if configured)

**Usage**: Quick sharing, documentation, client updates

#### CSV Format (Session Data)
Spreadsheet-compatible data with columns:
- Session date/time
- Duration (hours)
- Active time (hours)
- Idle time (hours)
- Idle count
- Playtest count
- Playtest duration (hours)

**Usage**: Excel analysis, charts, data processing

#### JSON Format (Complete Export)
Full data structure export including:
- All session details
- Roadmap categories and tasks
- Budget configuration
- Reminder settings
- Project metadata

**Usage**: Backup, data migration, external tool integration

### How to Export

1. Open **Window → Developer Buddy**
2. Navigate to **Reports** tab
3. Scroll to bottom of the tab
4. Click desired export button:
   - `Export as TXT` - Summary report
   - `Export as CSV` - Session data
   - `Export as JSON` - Complete data
5. File saves to: `Assets/DeveloperBuddy/Exports/`
6. Filename format: `ProjectName_Report_YYYYMMDD_HHMMSS.ext`

### Export Location

```
Assets/DeveloperBuddy/Exports/
├── MyProject_Report_20251023_143022.txt
├── MyProject_Sessions_20251023_143025.csv
└── MyProject_FullData_20251023_143028.json
```

**Note**: Export folder creates automatically on first export.

## 📝 Version

Current implementation includes all core features and optimization systems.

## 🤝 Contributing

This tool is designed for Unity Asset Store distribution.

---

**Developer Buddy** - Track your Unity development time efficiently 🚀
