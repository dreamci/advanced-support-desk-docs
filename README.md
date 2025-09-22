# Advanced Support Desk for Filament

[![Latest Version on Packagist](https://img.shields.io/packagist/v/your-vendor/your-package-name.svg?style=flat-square)](https://packagist.org/packages/your-vendor/your-package-name)
[![Total Downloads](https://img.shields.io/packagist/dt/your-vendor/your-package-name.svg?style=flat-square)](https://packagist.org/packages/your-vendor/your-package-name)

A **Filament 4 plugin** that provides a complete support ticket desk for your Laravel application. Designed for teams who want to manage customer tickets directly inside their Filament admin panel.

Easily create, track, and manage customer support requests with features like email integration, internal notes, assignments, and more.



---

## ✨ Features

-   ✅ **Ticket Management**: Create, assign, and track support tickets with status, priority, and department fields.
-   ✅ **Requester & Client Integration**: Automatically link tickets to your application's users (clients) with name and email.
-   ✅ **Email Import (IMAP/POP3)**: Automatically fetch emails from a mailbox and convert them into tickets or replies.
-   ✅ **Direct Email Replies**: Reply to tickets directly from the Filament panel; replies are sent to the requester via email.
-   ✅ **Notifications**: Automated email notifications for staff and requesters, plus in-app notifications for staff assignments and replies.
-   ✅ **Internal Notes**: Collaborate with your team by adding private notes to tickets that are invisible to the requester.
-   ✅ **File Attachments**: Upload and manage file attachments for both tickets and individual messages.
-   ✅ **Dashboard Widgets**: Includes "All Tickets" and "My Assigned Tickets" widgets to get a quick overview.
-   ✅ **Filtering & Badges**: Filter tickets by status, priority, and department. The navigation badge shows the number of active tickets needing attention.
-   ✅ **Permission System**: Restrict access based on global admin status or department membership.
-   ✅ **Soft Deletes**: Safely move tickets to the trash, restore them, or force delete them permanently.

---

## 🚀 Installation

Getting started is easy. Just follow these steps.

1.  **Install the plugin via Composer:**
    ```bash
    composer require your-vendor/your-package-name
    ```

2.  **Run the migrations:**
    This will create the necessary tables for tickets, messages, departments, etc.
    ```bash
    php artisan migrate
    ```

3.  **Register the plugin in your Panel Provider:**
    In your `app/Providers/Filament/AdminPanelProvider.php` (or the panel provider you use), add the plugin to the `plugin()` method:
    ```php
    use Umnidev\AdvancedSupportDesk\AdvancedSupportDeskPlugin;

    public function panel(Panel $panel): Panel
    {
        return $panel
            // ...
            ->plugin(
                AdvancedSupportDeskPlugin::make()
            );
    }
    ```

---

## ⚙️ Configuration

Publish the configuration file to customize the plugin's behavior.

```bash
php artisan vendor:publish --tag="advanced-support-desk-config"
