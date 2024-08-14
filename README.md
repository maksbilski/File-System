# Virtual Disk File System

## Overview

This project implements a basic file system within a virtual disk environment using the C programming language. The file system operates within a single large file that acts as a "virtual disk," allowing users to perform fundamental file operations such as creating, copying, deleting, and managing files.

## Features

- **Virtual Disk Creation**: Initialize a virtual disk within a file of a specified size.
- **File Copying**: 
  - Copy files from the Minix system to the virtual disk.
  - Copy files from the virtual disk back to the Minix system.
- **File Management**:
  - List all files stored on the virtual disk.
  - Delete files from the virtual disk.
- **Disk Management**:
  - Display the current state of the virtual disk, including the allocation map and the status (free/occupied) of disk blocks.
- **Disk Deletion**: Remove the virtual disk file from the system.

## Implementation Details

- **Single-Level Directory Structure**: The file system uses a simple directory structure where each entry contains the file name, size, and location on the virtual disk.
- **Allocation Map**: The system tracks the allocation of disk blocks to ensure efficient storage and prevent fragmentation.
- **Error Handling**: The system handles scenarios such as insufficient disk space, duplicate file names, and attempts to delete non-existent files.

## Testing

The project includes several shell scripts for testing various scenarios, such as:

- **Exceeding File Size**: Tests how the system handles attempts to copy files larger than the available disk space.
- **File Does Not Exist**: Tests system behavior when trying to delete a file that does not exist on the virtual disk.
- **Gap Filling Test**: Evaluates the system's ability to allocate space in non-contiguous blocks.
- **Name Already on System**: Tests handling of duplicate file names within the virtual disk.
- **Non-Contiguous Allocation**: Assesses the system's support for files that are stored in non-contiguous blocks.
- **Not Sufficient Space**: Checks how the system responds when there is not enough space to store a new file.

## Build and Run

To compile and run the project, use the provided `Makefile`. The following commands will build the project and run the virtual disk system:

```bash
make
./virtual_disk
```

## Usage

After compiling, you can interact with the virtual disk file system using the command-line interface. The program supports various commands to manage files and disk operations.

### Example Commands:

- **Create a Virtual Disk**:
  ```bash  
  ./virtual_disk create <disk_name> <size>
  ```

- **Copy File to Virtual Disk**:
  ```bash  
  ./virtual_disk copy_to <disk_name> <source_file>
  ```

- **Copy File from Virtual Disk**:
  ```bash  
  ./virtual_disk copy_from <disk_name> <file_name>
  ```

- **List Files on Virtual Disk**:
  ```bash
  ./virtual_disk list <disk_name>
  ```

- **Delete a File from Virtual Disk**:
  ```bash
  ./virtual_disk delete <disk_name> <file_name>
  ```

- **Show Disk Usage**:
  ```bash  
  `./virtual_disk usage <disk_name>`
  ```

## Overview

This project implements a basic file system within a virtual disk environment using the C programming language. The file system operates within a single large file that acts as a "virtual disk," allowing users to perform fundamental file operations such as creating, copying, deleting, and managing files.

## Features

- **Virtual Disk Creation**: Initialize a virtual disk within a file of a specified size.
- **File Copying**:
  - Copy files from the Minix system to the virtual disk.
  - Copy files from the virtual disk back to the Minix system.
- **File Management**:
  - List all files stored on the virtual disk.
  - Delete files from the virtual disk.
- **Disk Management**:
  - Display the current state of the virtual disk, including the allocation map and the status (free/occupied) of disk blocks.
- **Disk Deletion**: Remove the virtual disk file from the system.

## Implementation Details

- **Single-Level Directory Structure**: The file system uses a simple directory structure where each entry contains the file name, size, and location on the virtual disk.
- **Allocation Map**: The system tracks the allocation of disk blocks to ensure efficient storage and prevent fragmentation.
- **Error Handling**: The system handles scenarios such as insufficient disk space, duplicate file names, and attempts to delete non-existent files.

## Testings

The project includes several shell scripts for testing various scenarios, such as:

- **Exceeding File Size**: Tests how the system handles attempts to copy files larger than the available disk space.
- **File Does Not Exist**: Tests system behavior when trying to delete a file that does not exist on the virtual disk.
- **Gap Filling Test**: Evaluates the system's ability to allocate space in non-contiguous blocks.
- **Name Already on System**: Tests handling of duplicate file names within the virtual disk.
- **Non-Contiguous Allocation**: Assesses the system's support for files that are stored in non-contiguous blocks.
- **Not Sufficient Space**: Checks how the system responds when there is not enough space to store a new file.
  
## License

This project is open-source and available under the MIT License.
