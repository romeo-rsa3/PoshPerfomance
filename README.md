# PoshPerformance

A small Windows Forms (.NET Framework 4.7.2) sample application and Visual Studio solution. The project currently contains a minimal default Form (Form1) and a local SQL Server database file (Main.mdf). It appears to be an early-stage or template project — there is no application-specific business logic yet.

## Stack
- Language: C#
- Framework: .NET Framework 4.7.2 (Windows Forms)
- Notable libraries: System.Windows.Forms, System.Data, System.Drawing, System.Net.Http

## Repository layout
```
PoshPerfomance/                - repository root
  WindowsFormsApp1.sln         - Visual Studio solution
  WindowsFormsApp1.csproj      - project file (TargetFramework v4.7.2)
  Program.cs                   - application entry point (Application.Run(Form1))
  Form1.cs                     - main form code-behind (minimal)
  Form1.Designer.cs            - Windows Forms designer-generated UI
  Form1.resx                   - resources for Form1
  App.config                   - application configuration
  Main.mdf                     - local SQL Server database file (copied to output)
  Main_log.ldf                 - database log file
  project25.zip                - archive included in repo (contents not inspected)
  README.md                    - this file
  .gitignore                   - git ignore rules
  .gitattributes               - attributes
```

How it fits together
- Program.cs is the process entry point and launches the WinForms message loop. The UI is defined by Form1 (Form1.cs + Form1.Designer.cs); at the moment Form1 contains no custom logic beyond the default template.
- The project file references the database files (Main.mdf / Main_log.ldf) and will copy them to the output directory on build.

## Requirements
- Windows with Visual Studio (2019/2022) or MSBuild installed
- .NET Framework 4.7.2 runtime and developer targeting pack
- If you intend to use the included .mdf database, a SQL Server instance or LocalDB is required to attach/use it

## Build & run
From Visual Studio
1. Open `WindowsFormsApp1.sln` in Visual Studio.
2. Build the solution (Build → Build Solution).
3. Run (F5) to start the application.

From the command line (Developer Command Prompt / with MSBuild available)
```bash
# Build (Debug)
msbuild WindowsFormsApp1.sln /p:Configuration=Debug
# Run the built executable
bin\Debug\WindowsFormsApp1.exe
```

Notes
- The repository currently looks like a skeleton/template app. There is no application-specific functionality implemented in Form1.
- `Main.mdf` and `Main_log.ldf` are included and set to copy to the output directory. These are binary SQL Server files (each ~8MB). If they are not required in the VCS, consider removing them and adding an appropriate migration or seed script instead.
- `project25.zip` is present in the repo; its purpose is not documented here.

Contributing
- If you plan to continue work here, please add a short description of the project's purpose and intended features, and replace the placeholder Form1 with the real UI/logic.
- Open issues or PRs with feature descriptions, design notes, or specific tasks.

License
- No license is included in the repository. Add a LICENSE file if you intend to make this project public with a specific license.

Questions / next steps
- I inspected the solution, project file, Program.cs, Form1 (code + designer), and the project file. If you want, I can:
  - (1) commit this README (done),
  - (2) remove or git-ignore the database files and add a migration/seed script, or
  - (3) expand the README with usage examples once you describe the app's purpose.
