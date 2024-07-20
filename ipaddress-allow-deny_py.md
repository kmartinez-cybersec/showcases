<h1>Python Algorithm for File Updates</h1>
<h2>Description</h2>
A file that identifies employees that can access restricted content must be updated. Employees are identified by IP address. There is a remove list that identifies IP addresses that must be removed from the allow list. The following Python program is made to automatically remove an address from the allow list if it is found to be on the remove list.
<h2>Walkthrough</h2>
<h3>Open the file that contains the allow list; Read the file contents</h3>

![image](https://github.com/user-attachments/assets/1062166e-4adc-4f2b-bd6e-9c22ebc3c183)


The “allow_list.txt” file is assigned to the `import_file` variable.
The `with` keyword is then used to open `allow_list.txt` in read mode, stored as the variable `file`.

The file is read using the `.read()` method, and the contents of the file are assigned to the `ip_addresses` variable.

<h3>Convert the string into a list</h3>

![image](https://github.com/user-attachments/assets/358b60c1-eba7-435a-b017-0319bd607827)

The `.split()` method is used to convert the `ip_addresses` string to a list that is reassigned to the same variable.

<h3>Iterate through the remove list and remove addresses found</h3>

![image](https://github.com/user-attachments/assets/5d640376-4bac-4bff-a81b-aceabc278d3f)

The header of an iterative statement is set up using a `for` loop to iterate through each address in the `ip_addresses` list.

A conditional statement is built using `if` that checks if variable `address` is in the `remove_list` list. If it is in the remove list, the address is removed from the `ip_addresses` list using the `.remove()` method. This is only possible because the `ip_addresses` list contains only unique IP addresses with no repeats.

<h3>Update the file with the revised list of IP addresses</h3>

![image](https://github.com/user-attachments/assets/5f80520d-7c9c-4f4f-9dfd-092ec7a55897)

The `ip_addresses` list must be converted back to a string. The `.join()` method is used to do this, joining each element in the list with a newline character so each element will be on its own line.

The `with` keyword is used to open `allow_list.txt`, stored in the `import_file` variable, to read it and store it as variable `file`. Then, the (formerly list, now string) variable `ip_addresses` is written to the file.

<h2>Final function</h2>

```py
# Algorithm for file updates in Python
def update_file(import_file, remove_list):
    # Open the file that contains the allow list
    with open(import_file, "r") as file:

        # Read the file contents
        ip_addresses = file.read()
        
    # Convert ip_addresses from string to list
    ip_addresses = ip_addresses.split()

    # Iterate through remove list
    for address in ip_addresses:
        
        # Remove IP addresses that are on the remove list
        if address in remove_list:
            ip_addresses.remove(address)

    # Update file with revised list of IP addresses
    # Convert ip_addresses back to a string
    ip_addresses = "\n".join(ip_addresses)
    # Write over original file
    with open(import_file, "w") as file:
        file.write(ip_addresses) 

```
