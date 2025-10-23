# Howard Honors Housing Room Matching System

An automated priority-based room assignment system for Howard University's honors housing program.

## Overview

This prototype system automates the room matching process for honors students, which currently takes days of manual work and causes significant stress for residential life staff. The system processes student and room data, applies priority rules, and generates assignments in seconds.

## Features

- **Automated Priority Matching**: Automatically assigns rooms based on honors status, year, and account holds
- **CSV Import/Export**: Easy data upload and download of results
- **Real-time Processing**: See the matching algorithm run in real-time
- **Comprehensive Results**: View room assignments, waitlist, and excluded students
- **Export Reports**: Download CSV files for integration with other systems

## Priority Rules

The system implements the following priority hierarchy:

1. **Account Holds**: Students with holds are excluded from housing assignment
2. **Honors Status**: Only honors students are eligible for honors housing
3. **Year Priority**: Within honors students:
   - Freshman (highest priority)
   - Sophomores
   - Juniors
   - Seniors (lowest priority)

## How to Use

### Step 1: Prepare Your Data

Create two CSV files:

**Students CSV** (required columns):
```csv
student_id,name,email,year,honors,has_hold
HU001,John Doe,john.doe@howard.edu,freshman,yes,no
HU002,Jane Smith,jane.smith@howard.edu,sophomore,yes,no
```

- `year`: Must be one of: freshman, sophomore, junior, senior
- `honors`: yes or no
- `has_hold`: yes or no

**Rooms CSV** (required columns):
```csv
building,room_number,capacity,floor,room_type
Drew Hall,101,2,1,double
Drew Hall,102,1,1,single
```

### Step 2: Upload Data

1. Navigate to the Room Matching System dashboard
2. Click "Download Templates" to get sample CSV files
3. Upload your student and room CSV files
4. Click "Load Data" to import the information

### Step 3: Run Matching

1. Click "Run Matching Algorithm"
2. Watch the real-time processing
3. The system will:
   - Filter students with account holds
   - Prioritize honors students by year
   - Assign rooms in priority order
   - Create a waitlist for unmatched students

### Step 4: Review Results

1. Click "View Results" to see:
   - **Room Assignments**: All successfully matched students
   - **Waitlist**: Students who couldn't be placed (no rooms available)
   - **Excluded Students**: Students with account holds
2. Use the search boxes to filter results
3. Switch between tabs to view different categories

### Step 5: Export Results

1. Click "Export Results" to download:
   - `room_assignments.csv`: All room assignments
   - `waitlist.csv`: Students on the waitlist
   - `excluded_students.csv`: Students excluded due to holds
2. Share these files with relevant staff or import into other systems

## Technical Details

### Architecture

- **Frontend**: Pure HTML/CSS/JavaScript (no frameworks)
- **Storage**: Browser localStorage for data persistence
- **Processing**: Client-side JavaScript algorithm
- **Deployment**: Static hosting via GitHub Pages

### Data Flow

1. CSV files are parsed in the browser
2. Data is stored in localStorage
3. Matching algorithm runs client-side
4. Results are stored in localStorage
5. Results can be exported as CSV files

### Browser Compatibility

Works on all modern browsers:
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## Benefits

### Time Savings
- **Before**: Days of manual work, 100+ hours of staff time
- **After**: Minutes of automated processing

### Accuracy
- Eliminates human error in priority sorting
- Consistent application of rules
- Complete audit trail

### Stress Reduction
- No more late nights during assignment periods
- Clear, transparent process
- Immediate results

## Future Enhancements

Potential improvements for a production system:

1. **Backend Integration**: Connect to existing student information systems
2. **Real-time Updates**: Sync with live student and room databases
3. **Email Notifications**: Automatically notify students of assignments
4. **Roommate Preferences**: Support student pairing requests
5. **Advanced Filters**: Additional criteria (major, special needs, etc.)
6. **Historical Reports**: Track assignments over multiple semesters
7. **User Authentication**: Role-based access for different staff members

## Support

For questions or issues with the system, contact the development team or refer to the in-app help sections.

## License

© 2025 Howard University Housing Office
