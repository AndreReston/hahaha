Setup and testing instructions

1) Add SQLite JDBC to the project

- Download a sqlite-jdbc jar (recommended): sqlite-jdbc-3.40.0.0.jar (or latest) from https://github.com/xerial/sqlite-jdbc/releases
- In NetBeans: right-click the project `JavaApplication1` -> Properties -> Libraries -> Add JAR/Folder -> select the downloaded jar.
- Clean & Build the project.

2) Quick navigation test (no DB required)

- I commented out the `config.initDB();` call in `NewJFrame` so the `GET STARTED` button will open the login frame without the JDBC jar.
- To re-enable DB initialization, edit `src/javaapplication1/NewJFrame.java` and remove the `//` before `config.initDB();`.

3) Verify DB connectivity and contents with the TestDB helper

- There is a `TestDB` class at `src/javaapplication1/TestDB.java` that initializes the DB and lists `users`.
- After adding the JDBC jar, run `TestDB` (right-click file -> Run File). It will create `computerdb.db` if needed and show current users.

4) If registration/login fail

- Run the application from NetBeans and check the Output window for exceptions (ClassNotFoundException indicates missing sqlite-jdbc jar).
- If you prefer, I can place a sqlite-jdbc jar inside a `lib/` folder in the project for you — tell me if you want that.

5) Re-enable DB initialization

- After adding the jar, open `src/javaapplication1/NewJFrame.java` and change the `jButton1ActionPerformed` to:

    config.initDB();
    NewJFrame1 nf = new NewJFrame1();
    nf.setVisible(true);
    this.dispose();

That's it — tell me if you want me to add the jar into the workspace (I can add a `lib/` folder and a placeholder file, but I cannot download external jars without your approval).