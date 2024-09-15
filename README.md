# Templater CLI

Templater CLI is a customizable command-line interface (CLI) application designed to help you manage and automate repetitive tasks like creating templates, sections, managing `.gitkeep` files, and executing various scripts. The CLI is configured through a JSON file, allowing you to define custom commands for different platforms.

### Features

- **Create Sections and Templates**: Easily create and manage project sections and templates.
- **Manage `.gitkeep` Files**: Add or remove `.gitkeep` files in directories based on their content.
- **Run Scripts**: Execute Python, Bash, and Batch scripts according to the operating system.
- **Customizable Commands**: Define and manage commands via a configuration file.

### Requirements

- Python 3.x
- Operating System:
  - Windows for Batch scripts (`.bat`)
  - Linux for Bash scripts (`.sh`)
  - Python scripts are supported on both platforms

### Installation

1. **Clone the Repository**

   ```
   git clone https://github.com/yourusername/templater-cli.git
   cd templater-cli
   ```

2. **Install Dependencies**

   Install the required Python packages:

   ```
   pip3 install -r requirements.txt
   ```

3. **(Optional) Make the Python Script Executable**

   On Linux, make the Python script executable:

   ```
   chmod +x templater.py
   ```

### Configuration

The CLI uses a `configuration.json` file to define custom commands for different platforms and script types.

#### Example `configuration.json`

```
{
  "scripts": [
    {
      "command": "t",
      "description": "Create Template",
      "path": "./scripts/create_template.py",
      "type": "python",
      "platform": "*"
    },
    {
      "command": "s",
      "description": "Create Section",
      "path": "./scripts/create_section.py",
      "type": "python",
      "platform": "*"
    },
    {
      "command": "ec",
      "description": "Execute Current Code",
      "path": "./scripts/execute_code.py",
      "type": "python",
      "platform": "*"
    },
    {
      "command": "eo",
      "description": "Execute Other Code",
      "path": "./scripts/execute_other_code.py",
      "type": "python",
      "platform": "*"
    },
    {
      "command": "add-gitkeep",
      "description": "Add .gitkeep to empty directories",
      "path": "./scripts/gitkeep_adder.py",
      "type": "python",
      "platform": "*"
    },
    {
      "command": "rm-gitkeep",
      "description": "Remove .gitkeep from non-empty directories",
      "path": "./scripts/gitkeep_remover.py",
      "type": "python",
      "platform": "*"
    }
  ]
}
```

### Fields in the Configuration File

- **command**: The keyword to invoke the script.
- **description**: A short description of what the script does.
- **path**: The file path of the script to be executed.
- **type**: Type of script (Python, Bash, Batch).
- **platform**: The platform where the command can be executed (windows, linux, * for all platforms).

### Usage

- Run the Templater CLI:

  ```
  python3 templater.py
  ```

- Enter your command based on the configured commands in `configuration.json`.

  ```
  Enter your command: t
  ```

- Type `help` to display available commands or `q` to quit the application.

### Script Details

- **templater.py**: This is the main script for the Templater CLI. It loads the configuration, displays help, and executes commands based on user input. It supports running Python, Bash, and Batch scripts based on the platform.

### `scripts` Directory

- **Python Scripts**: Used for various tasks such as creating sections, templates, and managing `.gitkeep` files.
- **Batch and Bash Scripts**: Platform-specific scripts for starting and running the application.

### License

This project is licensed under the MIT License - see the LICENSE file for details.

### Contributing

Contributions are welcome! Please submit a pull request or open an issue for any bugs or improvements.

### Contact

For any questions or issues, please contact developer.anilkumars@gmail.com.
