# OnlineMusicStreaming

🎧 Symphony - Java Music Streaming Desktop AppA fully functional desktop music streaming platform inspired by Spotify. Built using Java Swing and MySQL, adhering to strict MVC architecture and academic coding standards.🎯 Project Highlights (Rubric Alignment)This project is engineered to demonstrate advanced Java concepts required for Review 1, ensuring robust performance and clean code structure.ConceptImplementation DetailsOOP PrinciplesUtilizes Inheritance (User → Admin/Artist), Polymorphism for dashboard rendering, and Encapsulation in Model classes.MultithreadingImplements SwingWorker and ExecutorService to handle music playback and database fetching without freezing the UI.CollectionsExtensive use of ArrayList for playlist management and HashMap for caching user sessions.JDBC & Transac.ACID compliant transactions used during playlist creation (updating multiple tables) and strict PreparedStatement usage for security.Exception HandlingCustom exceptions like InvalidEmailException and MusicNotFoundException ensure graceful error management.👥 User Roles & FeaturesThe application features a role-based login system with distinct dashboards.1. 🛡 AdministratorContent Moderation: Review and approve/reject songs uploaded by artists.System Oversight: View all registered users and content status.2. 🎸 ArtistMusic Upload: Upload songs with metadata (Title, Album, Genre).Portfolio Management: View status of uploaded tracks (Pending/Approved).3. 🎧 ListenerPlayback Controls: Play, Pause, Next, Previous, and Volume controls.Smart Search: Filter music by Title, Album, or Artist.Playlist System: Create custom playlists and manage tracks.Social: Follow favorite artists to stay updated.🏗 Project ArchitectureThe project follows the MVC (Model-View-Controller) pattern combined with the DAO (Data Access Object) pattern to separate logic from the interface.Plaintextsrc/
├── 📂 ui/                   # View Layer (Swing Components)
│   ├── LoginFrame.java
│   ├── MainFrame.java
│   └── PlaylistManagerDialog.java
├── 📂 service/              # Business Logic Layer
│   ├── AuthService.java
│   ├── MusicService.java
│   └── PlaylistService.java
├── 📂 dao/                  # Data Access Layer (JDBC)
│   ├── DBConnection.java    # Singleton Database Connection
│   ├── UserDAO.java
│   ├── MusicDAO.java
│   └── PlaylistDAO.java
├── 📂 models/               # POJO Classes
│   ├── User.java            # Parent Class
│   ├── Music.java
│   └── Playlist.java
├── 📂 exceptions/           # Custom Error Handling
│   ├── InvalidEmailException.java
│   └── MusicNotFoundException.java
└── Main.java                # Entry Point
🛠 Tech StackFrontend: Java Swing (JFrame, JPanel, JTable, Custom Layouts).Backend: Java SE (Standard Edition).Database: MySQL Community Server 8.0.Concurrency: java.util.concurrent (ExecutorService) & javax.swing.SwingWorker.Audio: Java Sound API (simulated for local file playback).🚀 Installation & Setup1. Database ConfigurationRun the following SQL commands in your MySQL Workbench to initialize the schema:SQLCREATE DATABASE musicapp;
USE musicapp;
-- Import the tables provided in the schema file (users, music, playlists, etc.)
2. Connect the AppNavigate to src/dao/DBConnection.java and update your credentials:Javaprivate static final String URL = "jdbc:mysql://localhost:3306/musicapp";
private static final String USER = "root";  // Your MySQL Username
private static final String PASS = "your_password"; // Your MySQL Password
3. RunCompile and run Main.java.Admin Login: admin@mail.com | admin123Artist Login: artist@mail.com | artist123
