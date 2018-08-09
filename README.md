# Clojure Dev Environment Setup

## Instructions

  1. Download and install the Java JDK 1.8 (do not get the demo and samples version)
http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

  Check if Java is on your PATH by opening either a terminal or a command prompt and typing “java -version”
  You should see something like this:

  ```
  Java(TM) SE Runtime Environment (build 1.8.0_131-b11)

  Java HotSpot(TM) 64-Bit Server VM (build 25.131-b11, mixed mode)
  ```

  Make sure that the version is 1.8 or greater.

  2. If Java is not on your path, Google “How to add to your path <your OS>” and follow the instructions. For Mac / Linux, I would recommend adding to your path in the .bash_profile (assuming you are using Bash). This step is not complete until the previous step works. On Windows, you may need to restart your computer for path additions to show up. On Mac/Linux, you may need to “source ~/.bash_profile”

  3. Install Git (https://git-scm.com/) and make sure it is on your path

  4. Install Leiningen (https://leiningen.org/)

  5. Check if Leiningen is on your path by opening either a terminal or command prompt and typing:

  ```
  lein –version
  ```

  You should see something like this:

  ```
  Leiningen 2.7.1 on Java 1.8.0_131 Java HotSpot(TM) 64-Bit Server VM
  ```

  6. Install Atom (https://atom.io/) -- Do not use an older version than 1.18 –  only the official latest version for the class will be supported.

  7. Use the Atom package manager "apm" command to install these plugins from the command line (or you can do it manually through preferences install):

  ```
  apm install platformio-ide-terminal parinfer lisp-paredit rainbow-delimiters proto-repl ink  atom-beautify atom-file-icons hasklig advanced-open-file
  ```
  8. Install joker from: https://github.com/candid82/joker and make sure it is on your path

  9. Use the "apm" command to install linter-jocker: "apm install linter-joker"

  10. Clone the CSX278-DevEnvTest repo by opening a terminal or command prompt, changing to a directory where you would like to store it, and then running the command:

  ```
  git clone https://github.com/juleswhite/CSX278-DevEnvTest
  ```

  11. Open a terminal or command prompt and change to the directory that you just cloned (make sure there is a “src” folder)

  12. Copy the contents of either the `mac-keymap.cson` or `windows-keymap.cson`
  into your Atom keyboard.cson (you can open it from within Atom by going to the
  Atom or File menu and selecting the Keymap option -- it is also available in
  the .atom configuration directory). Make sure and save the changes.

  12. In the terminal from your project directory, run the command:

  ```
  lein run
  ```

  and you should see a welcome message. If you do not or you get an error, you made a mistake in one of your setup steps. Find and fix the mistake.

  14. Run the command:

  ```
  lein repl
  ```

  and you should see a message like this:

  ```
  nREPL server started on port 56244 on host 127.0.0.1 - nrepl://127.0.0.1:56244
  REPL-y 0.3.7, nREPL 0.2.12
  Clojure 1.8.0
  Java HotSpot(TM) 64-Bit Server VM 1.8.0_131-b11
      Docs: (doc function-name-here)
            (find-doc "part-of-name-here")
    Source: (source function-name-here)
   Javadoc: (javadoc java-object-or-class-here)
      Exit: Control+D or (exit) or (quit)
   Results: Stored in vars *1, *2, *3, an exception in *e
  ```

  Look for the `port` that the nREPL server was started on and remember it.

  Whenever you are working on Clojure, you will want to start a REPL for your
  project, write down the port number, and then connect to it from Atom, which
  we will do in the next step.

  15. Open Atom, File->“Add Project Folder”, and add the folder that you cloned. Make sure that you open the folder that you cloned and not its parent. If you do this correctly, a new project should show up that has a “src” folder at the top-level when you expand it.

  16. In Atom, open the file src/x278/core.clj

  17. Press “Cmd + r” (Mac) or "Ctrl + r" (Windows) (or run the Atom command "Proto Repl: Remote Nrepl Connection") 
  and enter the port number that you wrote down from the nRepl step. A new Protorepl “repl” 
  window should then open and you will see a message like this:

  ```
  REPL Instructions

  Code can be entered at the bottom and executed by pressing shift+enter.

  Try it now by typing (+ 1 1) in the bottom section and pressing shift+enter.

  Working in another Clojure file and sending forms to the REPL is the most efficient way to work. Use the following key bindings to send code to the REPL. See the settings for more keybindings.

  ctrl-alt-, then b
  Execute block. Finds the block of Clojure code your cursor is in and executes that.

  ctrl-alt-, s
  Executes the selection. Sends the selected text to the REPL.

  You can disable this help text in the settings.
  Starting remote REPL connection on localhost:55666Refreshing code...
  :reloading (asgnx.core asgnx.core-test)
  Refresh complete
  ```

  18. Place the cursor immediately after the last ")" following "(defn print-welcome” and BEFORE the “(defn –main” and press either “Cmd + Enter” (Mac) or
  "Ctrl + Enter" (Windows). You should see “#'user/print-welcome” print in the repl
  window.

  Cursor goes here:

  ```
  (defn print-welcome []
      (println "  __        __   _                            _           ____ ____
    \\ \\      / /__| | ___ ___  _ __ ___   ___  | |_ ___    / ___/ ___|
     \\ \\ /\\ / / _ \\ |/ __/ _ \\| '_ ` _ \\ / _ \\ | __/ _ \\  | |   \\___ \\
      \\ V  V /  __/ | (_| (_) | | | | | |  __/ | || (_) | | |___ ___) |
       \\_/\\_/ \\___|_|\\___\\___/|_| |_| |_|\\___|  \\__\\___/   \\____|____/

          ____ _____ ___  _
    __  _|___ \\___  ( _ )| |
    \\ \\/ / __) | / // _ \\| |
     >  < / __/ / /| (_) |_|
    /_/\\_\\_____/_/  \\___/(_)
                            ")) <--put_the_cursor_here
  ```

  19. In the repl (not the core.clj source file!), type “(print-welcome)” and hit “Shift+Enter”

  20. If everything was done correctly, you should see the welcome message print in the repl. Copy this message VERBATIM and paste it in as the answer to the second question
  in the setup assignment.
