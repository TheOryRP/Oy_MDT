Discord: https://discord.gg/h5wD3THGEy

Oy_MDT - Advanced ESX Police & EMS MDT

 Oy_MDT is an advanced Mobile Data Terminal (MDT) system for FiveM ESX servers, designed for police and EMS roles. It includes real-time GPS tracking, a warrant system, ANPR (Automatic Number Plate Recognition), and much more!

Features:
Modern UI (tablet-style, responsive)

?? Warrant system (create, view, manage with player photos)

?? Real-time GPS tracking (live player & vehicle location tracking)

?? GPS logs (view historical movement of any player)

?? ANPR (Automatic Number Plate Recognition) (automatic plate scanning)

?? Supports Police & EMS

?? API ready (integrate with other scripts easily)

?? Permission-based access (jobs whitelist)

?? Opens with /mdt command

?? Easy to configure (fully customizable UI & database)

?? Installation:
1?? Download & Install
Clone or download this repository into your resources/ folder:

bash
Copy
Edit
git clone https://github.com/yourusername/Oy_MDT.git
Import the provided esx_mdt.sql into your database.

2?? Add to server.cfg
Add this line to your server.cfg:

ruby
Copy
Edit
ensure Oy_MDT
3?? Restart the server
? Done! Use /mdt to open the system in-game.

??? Usage:
Open MDT: /mdt (only for allowed jobs: police, ambulance, etc.)

Close MDT: Press ESC

Warrant system: Add/view player warrants

Live GPS tracking: Automatically records player movement

ANPR System: Automatically scans plates and fetches data

?? Configuration:
Edit config.lua to change MDT settings:

lua
Copy
Edit
Config = {}

Config.AllowedJobs = {"police", "ambulance", "sheriff"}  -- Who can access MDT
Config.MaxGPSRecords = 100  -- GPS history limit
Config.EnableANPR = true  -- Enable/Disable ANPR system
??? Database Setup:
Oy_MDT requires a MySQL database. Use this script to create necessary tables:

sql
Copy
Edit
CREATE TABLE IF NOT EXISTS `mdt_warrants` (
    `id` INT AUTO_INCREMENT PRIMARY KEY,
    `citizen_id` VARCHAR(50) NOT NULL,
    `officer` VARCHAR(50) NOT NULL,
    `reason` TEXT NOT NULL,
    `created_at` TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE IF NOT EXISTS `mdt_gps_logs` (
    `id` INT AUTO_INCREMENT PRIMARY KEY,
    `citizen_id` VARCHAR(50) NOT NULL,
    `x` FLOAT NOT NULL,
    `y` FLOAT NOT NULL,
    `z` FLOAT NOT NULL,
    `timestamp` TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE IF NOT EXISTS `mdt_anpr` (
    `id` INT AUTO_INCREMENT PRIMARY KEY,
    `plate` VARCHAR(20) NOT NULL,
    `owner` VARCHAR(50) NOT NULL,
    `model` VARCHAR(50) NOT NULL,
    `notes` TEXT,
    `created_at` TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
??? Roadmap / Future Updates:
? Offline player warrants

? Police case management system

? Advanced evidence management

? Mobile version for FiveM tablets (e.g., iPads in police cars)

?? License:
This project is licensed under the MIT License – you are free to use, modify, and distribute it.

?? Support & Contributions:
Found a bug? Open an issue.

Want to contribute? Feel free to fork & submit a pull request!

?? Enjoy Oy_MDT and make your FiveM RP server even better! ??

