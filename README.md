# SubdomainRegistrarCloudflare
A PHP Program For Subdomain Registeration And Management Based On Cloudflare DNS.

# To-Do List

- [ ] Multi-Lingual Support
- [ ] Multi-Domain Support


# Step 1: Creating and Importing Database
Create a MySQL database in your server, and import `cloudflareNIC.sql`. Make sure to take note of your database name, username and password.

# Step 2: Configuring `config.php`

## 1. Database Configuration

Update the following constants with your database credentials:

```php
define('DB_HOST', 'your-database-host');        // e.g. localhost
define('DB_USER', 'your-database-username');
define('DB_PASS', 'your-database-password');
define('DB_NAME', 'your-database-name');
```

---

## 2. Registrar System Setup

Replace the following with your domain details:

```php
define('DOMAIN_NAME', 'example.com');           // Lowercase version
define('DOMAIN_NAME_UP', 'EXAMPLE.COM');        // Uppercase version
define('REGISTRAR_DOMAIN', 'registrar.example.com');  // Domain of the registrar system
```

---

## 3. Cloudflare Setup

Create a scoped API token with permissions for DNS:Read and DNS:Edit for your domain.

```php
define('CLOUDFLARE_API_KEY', 'your-cloudflare-api-token');
define('CLOUDFLARE_ZONE_ID', 'your-cloudflare-zone-id');
```
Get API Token From [hCaptcha dashboard]([https://dashboard.hcaptcha.com/](https://dash.cloudflare.com/profile/api-tokens).
Find your zone ID on the Overview tab for your domain in the Cloudflare dashboard.

---

## 4. HCaptcha Integration

Set up HCaptcha for bot protection.

```php
define('HCAPTCHA_SITE_KEY', 'your-hcaptcha-site-key');
define('HCAPTCHA_SECRET', 'your-hcaptcha-secret-key');
```

Get these from your [hCaptcha dashboard](https://dashboard.hcaptcha.com/).

---

## 5. Google Login Setup

Enable OAuth on [Google Cloud Console](https://console.cloud.google.com/) and get your credentials.
A more detailed guide is available at [Setting Up Google Login]([https://console.cloud.google.com/](https://documentation.commerce7.com/how-do-i-setup-google-login))
Follow the guide up until step 1 in the guide, you will have all of the informations you need for this step.

```php
define('GOOGLE_CLIENT_ID', 'your-google-client-id');
define('GOOGLE_CLIENT_SECRET', 'your-google-client-secret');
```

Use a redirect URI like:
```
https://your-registrar-domain.com/oauth_callback.php
```

---

## Final Step

After updating all the placeholders in `config.php`, save and deploy your application. Ensure file permissions and API scopes are properly set.





