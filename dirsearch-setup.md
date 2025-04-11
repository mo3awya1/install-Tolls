
# How to Set Up and Use Dirsearch

This guide will walk you through setting up **Dirsearch**, a web directory scanner, and creating a script to run it from anywhere in the terminal. 

## 1. Update the System (Optional but Recommended)
Update your system to ensure all packages are up-to-date:

```bash
sudo apt update && sudo apt upgrade -y
```

## 2. Install Git (If Not Already Installed)
If you don't have Git installed, use the following command:

```bash
sudo apt install git -y
```

## 3. Clone Dirsearch from GitHub
Clone the Dirsearch repository to your system:

```bash
git clone https://github.com/maurosoria/dirsearch.git
```

## 4. Navigate to the Dirsearch Folder
Move into the `dirsearch` directory:

```bash
cd dirsearch
```

## 5. Create a Virtual Environment
Create a virtual environment to manage dependencies:

```bash
python3 -m venv venv
```

## 6. Activate the Virtual Environment
Activate the virtual environment:

```bash
source venv/bin/activate
```

## 7. Install Required Dependencies
Install the required dependencies listed in `requirements.txt`:

```bash
pip install -r requirements.txt
```

## 8. Run Dirsearch Within the Virtual Environment
Test if Dirsearch is working by running the help command:

```bash
python dirsearch.py -h
```

## 9. Create a Script to Easily Run Dirsearch Anywhere
To run Dirsearch from anywhere without navigating to the directory, create a simple script:

1. Open a new file using `nano`:

```bash
nano dirsearchme.sh
```

2. Add the following script to `dirsearchme.sh`:

```bash
#!/bin/bash
cd ~/Tolls/dirsearch
source venv/bin/activate
python dirsearch.py "$@"
deactivate
```

3. Save and exit.

4. Make the script executable:

```bash
chmod +x dirsearchme.sh
```

5. Move the script to a location in your system's PATH:

```bash
sudo cp dirsearchme.sh /usr/local/bin/dirsearchme
```

   Alternatively, if you're using Go, move the script to the `go/bin` directory:

```bash
sudo cp dirsearchme.sh ~/go/bin/dirsearchme
```

6. Add the following line to your `.bashrc` or `.zshrc` file to include the `go/bin` directory in your PATH:

```bash
nano ~/.bashrc
```

Then, add the following at the end of the file:

```bash
export PATH=$PATH:$HOME/go/bin
```

7. Save and exit. Apply the changes by running:

```bash
source ~/.bashrc
```

## 10. Run Dirsearch from Anywhere in the Terminal
Now, you can run Dirsearch from anywhere in the terminal by simply using the command:

```bash
dirsearchme -u https://example.com -e php,html,js
```

## Conclusion
By following these steps, you've successfully set up Dirsearch and created a convenient script to run it from anywhere in the terminal. This method makes using Dirsearch easier and more efficient, saving you the trouble of navigating to its directory each time.
