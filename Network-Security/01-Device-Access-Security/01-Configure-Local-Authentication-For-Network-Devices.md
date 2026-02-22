# Configure Username and Enable Secret for Network Devices

In this task, I configure a **local username** and an **enable secret** on all network devices. This allows secure access to **privileged EXEC mode** and supports **remote management**.

---

## Credentials Used

| Setting | Value |
|---|---|
| Username | `daysean` |
| User Secret | `ccna` |
| Enable Secret | `ccna` |

 **Note:** These credentials are used for this **project only**. They are simple so logging in during testing is quick and easy.

---

## Step 1 - Enter Global Configuration Mode

### Enter global config mode

```bash
enable
configure terminal
```

### Step 2 - Configure the Enable Secret

```bash
enable secret ccna
```

### Step 3 - Create a Local Username

```bash
username daysean secret ccna
```

### Verify

#### Exit console and Enter

<img width="293" height="129" alt="verify-local-auth" src="https://github.com/user-attachments/assets/0300f4c0-9d47-44f0-ab53-57a863f61f1e" />

### Next Click ➡️ [Here](/Network-Security/01-Device-Access-Security/02-Secure-Console-Access-With-Local-Authentication.md) to continute to Secure Console Access!

