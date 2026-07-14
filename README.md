# GeoIP-Traffic-Analyzer-MaxMind-Wireshark-Integration
MaxMind is a technology company that tracks where internet traffic comes from. Its main service, GeoIP, links a user's IP address to their real-world location (like country, city, or internet provider). To connect MaxMind databases to Wireshark, you need to download the free GeoLite2 databases and point Wireshark to the folder. 
Why MaxMind?
During packet analysis, IP addresses alone don't tell you much … a string of numbers gives no immediate sense of where traffic is coming from or going to. Analysts often end up manually pasting IPs into a separate lookup tool just to get that context, which slows down triage, especially when there are dozens or hundreds of connections to review.
  
  Tools Used
- Wireshark
- MaxMind GeoLite2 / GeoIP2 database

  Setup & Installation

## Setup & Installation

### Step 1: Download MaxMind Database Files
1. Sign up or log in to your free MaxMind GeoLite2 account
2. Go to the Download Databases section
3. Download the following in **Binary / .mmdb format** (not CSV):
   - GeoLite2 City
   - GeoLite2 Country
   - GeoLite2 ASN (for Autonomous System details)
4. Extract the .mmdb files from their .tar.gz or .zip folders

### Step 2: Place the Files in the Wireshark Directory
1. Navigate to your Wireshark installation folder (e.g., `C:\Program Files\Wireshark` on Windows)
2. Create a new folder named `GeoIP` inside the Wireshark directory
3. Move all extracted .mmdb files into this GeoIP folder

### Step 3: Configure Wireshark Preferences
1. Open Wireshark
2. Go to **Edit > Preferences**
3. Expand **Name Resolution** in the left menu
4. Click **MaxMind database directories**, then **Edit**
5. Click **+**, browse to your GeoIP folder, select it
6. Click **OK**, then restart Wireshark

### Step 4: Verify Geolocation Data
1. Start a packet capture, stop after a few seconds
2. Select any packet, expand the **Internet Protocol (IPv4/IPv6)** layer
3. You'll see new fields for **Country, City, and ASN** mapped to that IP
4. Cross-check via **Statistics > Endpoints**
5. To view on a map, use the **Map** dropdown in the Endpoints window



![Image Alt](https://github.com/Mafiana/GeoIP-Traffic-Analyzer-MaxMind-Wireshark-Integration/blob/b9038e572528141ccb55131d01111dd576ecfd91/img/Wireshark_OCQeoVldcB.png)
![Image Alt](https://github.com/Mafiana/GeoIP-Traffic-Analyzer-MaxMind-Wireshark-Integration/blob/3541ee2d55399591351b940128794b12ec26ba51/img/chrome_u6SZHceJrf.png)
![Image Alt](https://github.com/Mafiana/GeoIP-Traffic-Analyzer-MaxMind-Wireshark-Integration/blob/3541ee2d55399591351b940128794b12ec26ba51/img/DDNrOqypKm.png)
