RoeGuPOS - Point of Sale & Inventory System
(C# WinForms, .NET Framework 4.8, SQL Server Express)

FILES IN THIS REPOSITORY
  ROEGUS_POS.zip                 the application (.exe) - unzip it and run it
  RoeGuPOS.zip                   the source code (Visual Studio solution)
  RoeGusPOS_Full_Database.sql    the complete database (tables, procedures, sample data)
  README.txt                     this guide

REQUIREMENTS (to run the .exe)
  - Windows 10 or 11
  - SQL Server Express (instance .\SQLEXPRESS)
  - SQL Server Management Studio (SSMS), only once, to run the database file
  Visual Studio is NOT needed to run the program. It is only needed to open the source code.

HOW TO RUN THE APPLICATION

Step 1 - Create the database
  1. Open SSMS. Server name: .\SQLEXPRESS   Authentication: Windows Authentication. Click Connect.
  2. Click File > Open > File and choose RoeGusPOS_Full_Database.sql.
  3. Click Execute (or press F5) and wait for "Commands completed successfully".
  4. In Object Explorer, right-click Databases > Refresh. "RoeGuPOS" should be listed.
     (If the script did not create it: right-click Databases > New Database, name it
      RoeGuPOS, open the script again, choose RoeGuPOS in the database dropdown
      at the top, and Execute.)

Step 2 - Start the program
  1. Unzip ROEGUS_POS.zip first (right-click > Extract All). Do not run it from inside the zip.
  2. Open the extracted folder and find  RoeGuPOS.WinForms  (Type: Application).
  3. Optional - make a desktop shortcut:
       right-click RoeGuPOS.WinForms > Show more options > Send to > Desktop (create shortcut)
  4. Double-click RoeGuPOS.WinForms (or the desktop shortcut) and log in below.
  (Keep the extracted folder where it is. The shortcut only points to it.)

  If your SQL Server has a different name than .\SQLEXPRESS, open
  RoeGuPOS.WinForms.exe.config in Notepad, change Data Source=.\SQLEXPRESS, and save.

LOGINS
  Admin    admin     Admin@123    everything, including Users
  Manager  manager   Manager@123  inventory, analytics, customers, sales
  Cashier  cashier   Cashier@123  sales and customers only

SOURCE CODE (RoeGuPOS.zip)
  Unzip it and open the .sln file in Visual Studio. Projects:
    RoeGuPOS.Domain     data models
    RoeGuPOS.Data       database access
    RoeGuPOS.Services   business rules and permissions
    RoeGuPOS.WinForms   screens (set as the startup project)
  Build with Build > Rebuild Solution, then press F5.

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
