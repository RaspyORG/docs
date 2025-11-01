# Installation Guide

This guide will walk you through how to **set up and install your Raspy instance** on a **local machine** or **cloud server**.

:::note[Windows Installations are NOT supported]
While you probably can install and configure a Raspy instance on Windows it is not supported or recommended.
Please if you can use Ubuntu Server, Debian or Arch Linux. Other Linux distros are still supported, but not mentioned in our documentation as many Linux distros share the same package managers, utilities and commands.
:::

---

## Linux Installation Guide

### 1. Connect to Your Server

If you’re installing Raspy on a **remote machine**, you’ll first need to connect via SSH.
*(If you’re already on the target machine, skip this step.)*

```bash
ssh root@[IP_ADDRESS]
```

Enter the root user’s password when prompted.

---

### 2. Install Git

We’ll use Git to clone the Raspy repository.

**Debian / Ubuntu:**

```bash
apt install git -y
```

**Arch Linux:**

```bash
pacman -S git
```

---

### 3. Clone the Raspy Repository

Download the Raspy source code from GitHub:

```bash
git clone https://github.com/RaspyORG/bot
cd bot
```

---

### 4. Install Node.js and Dependencies

Raspy runs on Node.js, so let’s install it and the required npm packages.

**Debian / Ubuntu:**

```bash
apt install nodejs npm -y
```

**Arch Linux:**

```bash
pacman -S nodejs npm
```

Then install all project dependencies:

```bash
npm install
```

---

### 5. Set Up Environment Variables

Create a `.env` file in the project root directory.
This file stores sensitive information like your Discord bot token, MongoDB credentials, and Roblox API keys.

Example `.env` file:

```
BOT_NAME=

# Discord bot credentials
DISCORD_TOKEN=
CLIENT_ID=
GUILD_ID=

# MongoDB connection string
MONGODB_URI=
DB_NAME=

# Roblox API credentials
ROBLOX_CLIENT_ID=
ROBLOX_CLIENT_SECRET=

# Hostname where the verification service is hosted
VERIFY_HOST=
```


:::warning[Keep your credentials safe!]
Never share your `.env` file publicly or commit it to GitHub.  
It contains private credentials that can give others full access to your bot and database.
:::

---

### 6. Configure Raspy

Open the configuration file:

```bash
nano config.json
```

Inside, you’ll find configuration options for your setup.
Each line includes comments explaining what to change.

Save and exit with:

```
CTRL + O  # Save file
ENTER     # Confirm
CTRL + X  # Exit nano
```

---

### 7. Start Raspy

Once everything is configured, you can start your Raspy instance:

```bash
node .    # or npm start
```

If the setup is correct, your bot should now be running

---

## Invite Your Discord Bot to a Server

Now that your bot is live, let’s invite it to your Discord server.

1. Open this URL in your browser, replacing `CLIENT_ID` with your bot’s **Application (Client) ID** from the [Discord Developer Portal](https://discord.com/developers/applications):

   ```
   https://discord.com/oauth2/authorize?client_id=CLIENT_ID&permissions=8&scope=bot%20applications.commands
   ```

2. Choose the server you want to add your bot to.

3. Click **Authorize** and complete the CAPTCHA if prompted.

Once authorized, your bot should appear online in your Discord server.

---

## You’re All Set!

Congratulations!
You’ve successfully installed and configured a **Raspy Instance**.
Your bot is now connected to Discord and ready to go.

If you’d like, you can continue by:

* Setting up systemd
* Exploring Raspy’s features and command list
* Contributing to the [Raspy GitHub repository](https://github.com/RaspyORG/bot)