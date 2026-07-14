# GeoIP-Traffic-Analyzer-MaxMind-Wireshark-Integration
MaxMind is a technology company that tracks where internet traffic comes from. Its main service, GeoIP, links a user's IP address to their real-world location (like country, city, or internet provider). To connect MaxMind databases to Wireshark, you need to download the free GeoLite2 databases and point Wireshark to the folder. 
Why MaxMind?
During packet analysis, IP addresses alone don't tell you much … a string of numbers gives no immediate sense of where traffic is coming from or going to. Analysts often end up manually pasting IPs into a separate lookup tool just to get that context, which slows down triage, especially when there are dozens or hundreds of connections to review.
  
  Tools Used
- Wireshark
- MaxMind GeoLite2 / GeoIP2 database

  Setup & Installation

  Step 1: Download MaxMind Database Files
1.	Sign up or log in to your free MaxMind GeoLite2 Account.
2.	Go to the Download Databases section.
3.	Download the following databases in Binary / .mmdb format (do not download the CSV versions):
o	GeoLite2 City
o	GeoLite2 Country
o	GeoLite2 ASN (for Autonomous System details)
4.	Extract the .mmdb files from their respective .tar.gz or .zip folders.

Step 2: 
1. Place the Files in the Wireshark Directory

2.	Navigate to your Wireshark installation folder (e.g., C:\Program Files\Wireshark on Windows).
3.	Create a new folder named GeoIP inside the Wireshark directory.

4.	Move all your extracted .mmdb files directly into this GeoIP folder.

Step 3: Configure Wireshark Preferences
1.	Open Wireshark.
2.	Go to Edit > Preferences.
3.	Expand Name Resolution on the left menu.
4.	Click on MaxMind database directories and hit the Edit button.
5.	Click the + (plus) button and browse to select the GeoIP folder you created earlier.
6.	Click OK to save and restart Wireshark.

Step 4: Verify Geolocation Data
1.	Start a packet capture and stop it after a few seconds.
2.	Select any packet and expand the Internet Protocol (IPv4/IPv6) layer in the packet details pane.
3.	You will now see new dropdowns indicating the Country, City, and ASN mapped to that specific IP address...also go to Endpoint to verify.
4.	To view in map…look at the left dropdown box named “map”



![Image Alt](https://github.com/Mafiana/GeoIP-Traffic-Analyzer-MaxMind-Wireshark-Integration/blob/b9038e572528141ccb55131d01111dd576ecfd91/img/Wireshark_OCQeoVldcB.png)
![Image Alt](https://github.com/Mafiana/GeoIP-Traffic-Analyzer-MaxMind-Wireshark-Integration/blob/3541ee2d55399591351b940128794b12ec26ba51/img/chrome_u6SZHceJrf.png)
![Image Alt](https://github.com/Mafiana/GeoIP-Traffic-Analyzer-MaxMind-Wireshark-Integration/blob/3541ee2d55399591351b940128794b12ec26ba51/img/DDNrOqypKm.png)
