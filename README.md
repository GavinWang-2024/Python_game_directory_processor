# Game Directory Processor

This Python script processes game directories, compiles the game code, and generates metadata for the games found within a specified source directory.

## Features

Find Game Directories: Searches for directories containing game code based on a specified pattern.
Copy and Overwrite: Copies game directories to a target location, overwriting existing directories.
Compile Game Code: Compiles the game code found within each directory.
Generate Metadata: Creates a JSON metadata file containing the names and count of the games processed.
 
## Requirements

Python 3.x

Go programming language (for compiling game code)


## Usage

Prepare your directories:

Create a source directory containing your game directories.
Ensure each game directory name includes the pattern "game".

Run the script:

```python3 game_directory_processor.py <source_directory> <target_directory>```
Replace <source_directory> with the path to your source directory and <target_directory> with the path to your desired target directory.



## Example

Given the following directory structure in source_directory:

```
source_directory/
├── game1_game
│   └── main.go
├── game2_game
│   └── main.go
```

Running the script with:

```python3 game_directory_processor.py source_directory target_directory```


Will result in:

```
target_directory/
├── game1
│   └── main (compiled binary)
├── game2
│   └── main (compiled binary)
└── metadata.json
```

## Functions

```find_all_game_paths(source)```: Finds all directories containing the specified game pattern.
```get_name_from_paths(paths, to_strip)```: Strips a specified substring from directory names.
```create_dir(path)```: Creates a directory if it does not exist.
```copy_and_overwrite(source, dest)```: Copies a directory and overwrites the destination if it exists.
```make_json_metadata_file(path, game_dirs)```: Creates a JSON file with game metadata.
```compile_game_code(path)```: Compiles Go code found in the specified directory.
```run_command(command, path)```: Runs a shell command in the specified directory.







