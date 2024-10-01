# Facial Recognition Attendance System with Flask API

This system allows students to seamlessly mark their attendance using their webcam and allows faculty to view the attendance sheet and student details.

## Getting Started

### Prerequisites

1. Python 3.x
2. MySQL
3. Flask
4. Required Python packages (listed in `requirements.txt`)

### Installation and Setup

1. **Folder Structure:**
   - Ensure all contents are placed in a folder named `nived`.
   - Delete `hi.txt` from the `ImagesUnknown` and `TrainingImages` folders.

2. **Update HTML Links:**
   - Open the `startTheSystem` folder.
   - Edit the `main.html` file and update the hyperlinks in the buttons according to your system's file paths.

3. **Install Dependencies:**
   - Run the following command to install the required Python packages:
     ```bash
     pip install -r requirements.txt
     ```

4. **Database Setup:**
   - Open MySQL Workbench and run the following SQL code to create the database and table:
     ```sql
     CREATE DATABASE IF NOT EXISTS `pythonlogin` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
     USE `pythonlogin`;

     CREATE TABLE IF NOT EXISTS `accounts` (
       `id` int(11) NOT NULL AUTO_INCREMENT,
       `username` varchar(50) NOT NULL,
       `password` varchar(255) NOT NULL,
       `email` varchar(100) NOT NULL,
       PRIMARY KEY (`id`)
     ) ENGINE=InnoDB AUTO_INCREMENT=2 DEFAULT CHARSET=utf8;

     INSERT INTO `accounts` (`id`, `username`, `password`, `email`) VALUES (1, 'test', 'test', 'test@test.com');
     ```

5. **Update MySQL Configuration:**
   - Open `app.py` and update the MySQL password and host name according to your MySQL server details.

6. **Start the System:**
   - Open a command prompt in the project folder and run:
     ```bash
     python app.py
     ```
   - Open another command prompt in the same folder and run:
     ```bash
     python main.py
     ```

7. **Open the Web Interface:**
   - Navigate to the `startTheSystem` folder and open `main.html` in your browser.

## Usage

### Student Side

1. Students will be directed to `studentside.html` where they can take their attendance using their webcam.
2. After pressing the "Take Attendance" button, a Python window will pop up in the taskbar.
3. Press "Track Image" and you will see a notification "Attendance Uploaded with Details".
4. The take attendance portal will close in two minutes after the faculty activates the plugin system.

### Faculty Side

1. Faculty must log in to the system using the provided credentials (username: `test`, password: `test`).
2. Faculty can see four options on their side of the website:
   - **New Student:** Opens a new window where faculty can enter a student's name and roll number and capture their image. After capturing, press "Train Image" to train the image.
   - **Student Details:** View stored student details.
   - **Plugin System:** Activate the attendance system, allowing students to take attendance.
   - **Show Attendance:** View uploaded attendance records with time and date.

3. Faculty must press the "Plugin System" button to enable students to mark their attendance.

4. Students can then go to the student portal, press "Take Attendance", and the attendance will be uploaded.

## Notes

- Ensure the faculty log in and activate the plugin system before students can take their attendance.
- The system will close the take attendance portal two minutes after the faculty activates the plugin system.
- Faculty can view the uploaded attendance records by pressing the "Show Attendance" button.

## Troubleshooting

- If the system does not start, check that all dependencies are installed correctly.
- Ensure MySQL server is running and the credentials in `app.py` are correct.
- Verify the HTML file paths are correctly set according to your system.

---

For further assistance, please refer to the documentation or contact me or any other contributors.
