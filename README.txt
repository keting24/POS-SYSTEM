RoeGuPOS - Point of Sale & Inventory System
(C# WinForms, .NET Framework 4.8, SQL Server Express)

CONTENTS
  Program\    the application (RoeGuPOS.WinForms.exe and its files - keep them together)
  Database\   RoeGuPOS.sql (the complete database: tables, procedures, sample data)
  README.txt  this guide

REQUIREMENTS
  - Windows 10 or 11
  - SQL Server Express (instance .\SQLEXPRESS)
  - SQL Server Management Studio (SSMS)

HOW TO RUN THE APPLICATION

Step 1 - Create the database
  1. Open SSMS. Server name: .\SQLEXPRESS   Authentication: Windows Authentication. Click Connect.
  2. Click File > Open > File and choose Database\RoeGuPOS.sql.
  3. Click Execute (or press F5).
     Wait for "Commands completed successfully".
  4. In Object Explorer, right-click Databases > Refresh. "RoeGuPOS" should be listed.
     (If the script did not create it: right-click Databases > New Database, name it
      RoeGuPOS, then open the script again, choose RoeGuPOS in the database
      dropdown at the top, and Execute.)

Step 2 - Check the connection setting
  1. Open Program\RoeGuPOS.WinForms.exe.config in Notepad.
  2. Find:  Data Source=.\SQLEXPRESS
     If your SQL Server has another name, change it, then save the file.

Step 3 - Start the program
  1. Unzip the submitted file first (right-click the zip > Extract All). Do not run
     the program from inside the zip.
  2. Open the extracted Program folder and find  RoeGuPOS.WinForms  (Type: Application).
  3. Optional - make a desktop shortcut:
       right-click RoeGuPOS.WinForms > Show more options > Send to > Desktop (create shortcut)
  4. Double-click RoeGuPOS.WinForms (or the shortcut on the desktop).
  5. Log in with one of the accounts below.
  (Keep the Program folder where it is. The shortcut only points to it.)

LOGINS
  Admin    admin     Admin@123    everything, including Users
  Manager  manager   Manager@123  inventory, analytics, customers, sales
  Cashier  cashier   Cashier@123  sales and customers only

QUICK TOUR
  Dashboard  today's sales, orders, low stock, recent orders
  New Sale   add products, pick a customer, use points, pay, print receipt
  Customers  add and search customers, loyalty points and history
  Inventory  add, edit and delete products, adjust stock, categories, bulk price
  Analytics  sales reports by date range
  Users      add users, roles, reset passwords (Admin only)
  Log out    bottom of the left sidebar

IF THE PROGRAM DOES NOT START
  - "Cannot open database" or "network-related error": press Windows + R, type
    services.msc, and make sure "SQL Server (SQLEXPRESS)" is Running. Then check the
    Data Source in the .config file.
  - "Invalid username or password": use the logins above (passwords are case-sensitive).
  - Windows asks about .NET Framework 4.8: install it from Microsoft (Windows 10/11 already have it).
