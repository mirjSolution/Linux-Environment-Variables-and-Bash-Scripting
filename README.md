# Linux Environment Variables & Bash Scripting

This README contains summarized notes and examples based on a comprehensive lecture on environment variables and bash scripting in Linux.

---

## 🧠 Concepts Covered

### 1. **Environment Variables**

- Key-value pairs defined for user or system configuration.
- Common variables:
  - `USER`: Current logged-in user.
  - `HOME`: User's home directory.
  - `SHELL`: Default shell program (`/bin/bash`, `/bin/zsh`, etc.).
  - `PATH`: List of directories with executable programs.

### 2. **Viewing Environment Variables**

```bash
printenv             # List all environment variables=
```

![Environment Variables](Images/printenv.png)

```bash
printenv USER        # Display value of a specific variable
```

![Environment User](Images/envuser.png)

```bash
printenv | grep DB   # Filter environment variables by keyword
```

![Filter Environment](Images/envfilter.png)

### 3. **Referencing Environment Variables**

```bash
echo $USER           # Using in shell
```

![Filter Environment](Images/envfilter.png)

### 4. **Creating/Exporting Environment Variables**

```bash
export DB_USER="admin"
export DB_PASS="secret"
```

### 5. **Unsetting Environment Variables**

```bash
unset DB_USER
```

### 6. **Persisting Environment Variables**

- **Per User**: Add to `~/.bashrc`

```bash
export DB_NAME="my_database"
```

- Reload with:

```bash
source ~/.bashrc
```

- **Globally**: Edit `/etc/environment` (requires sudo)

---

## ⚙️ Bash Script Example

```bash
#!/bin/bash

echo "Running setup..."
export DB_USER="dev_user"
echo "Database user: $DB_USER"
```

### Executing:

```bash
chmod +x script.sh
./script.sh
```

---

## 🔐 Why Use Environment Variables?

- Securely pass secrets (API keys, DB creds) to applications.
- Configure software for multiple environments (dev, test, prod).
- Avoid hardcoding sensitive or environment-specific data in code.

---

## 📁 Modifying $PATH

Add custom script directory:

```bash
export PATH="$PATH:/home/username/scripts"
```

Or in `.bashrc`:

```bash
PATH="$PATH:$HOME/scripts"
```

Then run your script globally:

```bash
myscript
```

---

## 💡 Summary

- Use `export` for temporary variables.
- Use `.bashrc` or `/etc/environment` for permanent ones.
- Use `printenv`, `grep`, and `$VAR` to read values.
- Securely store credentials and config options.

Environment variables make your scripts portable, configurable, and secure.

🧑‍💻 _Created by Rico John Dato-on_  
🔗 [LinkedIn](https://www.linkedin.com/in/rico-john-dato-on) • [Portfolio](https://ricodatoon.netlify.app)
