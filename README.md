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

## How the File System Works

### Inodes and Directory Structure

The file system utilizes an inode-based architecture, which is a common method in UNIX-like systems to manage files. Each file on the virtual disk is associated with an inode, which is a data structure that stores essential information about the file, such as:

- **File Name**: The name of the file.
- **File Size**: The size of the file in bytes.
- **Data Block Pointers**: Pointers to the blocks on the virtual disk where the actual file data is stored.
- **Metadata**: Additional information such as file creation date, last modified date, and access permissions (if applicable).

### Allocation Map

The allocation map is a critical component of the file system that keeps track of which blocks on the virtual disk are free and which are occupied. This map helps the file system efficiently manage disk space and minimize fragmentation.

- **Block Allocation**: When a new file is created or an existing file is extended, the allocation map is consulted to find free blocks on the virtual disk. These blocks are then marked as occupied, and the file's inode is updated with pointers to these blocks.
  
- **Fragmentation Handling**: The allocation map helps in reducing both internal and external fragmentation. Internal fragmentation is minimized by allocating only the necessary number of blocks based on the file size. External fragmentation is addressed by attempting to allocate contiguous blocks whenever possible, ensuring that the file data is stored sequentially on the disk.

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
