# Commit Message Generator

A Python script that automatically generates concise and meaningful Git commit messages based on staged changes using the Ollama API [Default-**Mistral**, you can use any].

## Features

- Analyzes `git diff` of staged changes
- Generates commit messages that start with a verb, are specific, and stay under 72 characters
- Allows user to accept or modify the suggested message
- Handles the commit process automatically
- Includes detailed logging

## Prerequisites

- Python 3.6+
- Git installed and configured
- [Ollama](https://ollama.ai/) installed and running
- Required Python packages: `requests`, `loguru`

## Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/kunald08/AutoCommit-Generator-AI.git
   cd commit-message-generator
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Ensure Ollama is running:
   ```bash
   ollama serve
   ```

## Usage

1. Stage your changes: `git add .`
2. Run the script: `com_ai` //this is the bash file which calls the git diff and use mistral model to suggestr messages
3. Review the suggested commit message:
   - Press Enter to accept the generated message
   - Or type your own message and press Enter
4. The script will commit the changes and provide feedback

## Example

```bash
>> git add .
>> com_ai
INFO: Suggested commit message: "Update README with installation steps"

Press Enter to accept, or type a new message:
INFO: Successfully committed changes!
INFO: Ready to push! Use 'git push origin' to push your changes.
```

## How It Works

1. Retrieves the git diff of staged changes
2. Sends the diff to Ollama API with a prompt for a commit message
3. Receives and processes the generated message
4. Prompts user for approval or modification
5. Executes the git commit with the final message

## Troubleshooting

- Ensure Ollama is running (`ollama serve`)
- Verify Git is properly configured
- Check that files are staged (`git add`)
- Confirm internet connectivity for API calls

## License

This project is licensed under the MIT License - see the LICENSE file for details.