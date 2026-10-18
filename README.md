# IT-HelpDesk
Deployment and Configuration of a Self-Hosted HESK IT Helpdesk &amp; Ticketing System

# HESK IT Helpdesk Deployment & Configuration

## 1. Project Overview

Deployed and configured **HESK**, a self-hosted IT helpdesk and ticket management system, on a Linux server using **Webmin** for server and database administration.

The deployment included uploading and extracting the HESK application, configuring a MySQL database and dedicated database user, completing the HESK web-based installation, and securing the installation by removing the installer after deployment.

---

## 2. Deployment Environment

- **Application:** HESK Helpdesk
- **Server:** Linux Server
- **Server Management:** Webmin
- **Web Server:** Apache/Nginx environment configured through the server
- **Database:** MySQL
- **Database Management:** Webmin MySQL module
- **Application Directory:** `/var/www/hesk`
- **Access:** `https://<SERVER-IP>/hesk`

---

## 3. HESK Application Deployment

### Step 1: Download HESK

The HESK application package was downloaded from the official HESK distribution source.

### Step 2: Upload HESK to the Server

Using **Webmin's file management interface**, the downloaded HESK package was uploaded to the Linux server.

### Step 3: Extract the Application

The uploaded HESK archive was extracted on the server, producing the HESK application directory.

### Step 4: Move HESK to the Web Root

The extracted `hesk` directory was moved into the server's web root directory:

```text
/var/www/
```

The resulting application path was:

```text
/var/www/hesk
```

---

## 4. MySQL Database Configuration

A dedicated MySQL database and database user were created for HESK through the **MySQL module in Webmin**.

### Step 5: Create the Database User

A dedicated MySQL user was created:

```text
Username: heskuser
```

Using a dedicated database account keeps the HESK application separate from other databases and services on the server.

### Step 6: Create the HESK Database

A dedicated database was created:

```text
Database: heskdb
```

### Step 7: Grant Database Permissions

The required permissions for the HESK database were granted to the dedicated MySQL user:

```text
heskuser → heskdb
```

This allowed HESK to create and manage the database tables required by the application.

---

## 5. HESK Web Installation

### Step 8: Access the HESK Installer

After placing the HESK application in the web root, the server was accessed through a web browser using:

```text
https://<SERVER-IP>/hesk
```

The HESK installation interface was displayed.

### Step 9: Configure the Database Connection

During the installation process, the database credentials created previously were supplied to the HESK installer:

```text
Database Name: heskdb
Database User: heskuser
```

The installer used these credentials to establish a connection between HESK and the MySQL database.

### Step 10: Complete Installation

The HESK installation wizard automatically configured the application and created the required database structure.

After the installation completed successfully, HESK became accessible through the configured web address.

---

## 6. Post-Installation Security

### Step 11: Remove the Installer

After confirming that HESK was successfully installed, the HESK installation file was deleted from the server.

Removing the installer prevents unauthorized users from attempting to rerun or interfere with the installation process.

---

## 7. Result

The HESK helpdesk was successfully deployed as a **self-hosted IT support and ticket management platform**.

The completed deployment provides a web-based interface through which users can submit support requests and administrators can manage and respond to IT support tickets.

### Key Skills Demonstrated

- Linux server administration
- Webmin server administration
- Web application deployment
- MySQL database administration
- Database user and permission management
- Self-hosted helpdesk deployment
- Web-based application configuration
- Basic post-installation security hardening
- IT service desk infrastructure
