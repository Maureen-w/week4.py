def main():
    filename = input("Enter the filename to read: ")

    try:
        with open(filename, 'r') as file:
            content = file.read()
            print("\nOriginal file content:\n")
            print(content)
    except FileNotFoundError:
        print(f"Error: The file '{filename}' does not exist.")
        return
    except IOError:
        print(f"Error: The file '{filename}' could not be read.")
        return

    # Modify content (example: convert to uppercase)
    modified_content = content.upper()

    # Create new filename
    new_filename = "modified_" + filename

    try:
        with open(new_filename, 'w') as new_file:
            new_file.write(modified_content)
        print(f"\nModified content written to '{new_filename}' successfully!")
    except IOError:
        print(f"Error: Could not write to file '{new_filename}'.")

if __name__ == "__main__":
    main()
