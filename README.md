# Raspi-Dashboard
**Raspberry Pi Dashboard Application v0.1.2-alpha**      
This application is intended for a 7inch 800x400 touchscreen. The application is a desktop dashboard that updates:
- Date and time
- Weather and forecast
- Google Calendar

This product is currently unfinished, and I am by no means a certified programmer. The product is quite janky and needs a lot of love. However, the application is functional... except the calendar portion is currently lacking an update feature. I plan on making the application more flush after I finish the foundation of the software.

Coming soon:
- Calendar update function
- High resolution icons
- Night time weather icons
- Deployable bash script

**Current Progress:**

<img width="792" alt="Screenshot 2023-12-27 at 6 51 50 PM" src="https://github.com/Heisenberg-UP/Raspi-Dashboard/assets/99283516/789649ef-d56b-475a-aec4-593d8bdf3dd4">  


**Installation Guide:**

1. Clone the repository.
   ```bash
   git clone https://github.com/Heisenberg-UP/Raspi-Dashboard.git
   ```

2. Move into the repository folder.
   ```bash
   cd Raspi-Dashboard
   ```

3. Create a virtual python environment.
   ```bash
   python3 -m venv env
   source env/bin/activate
   ```

4. Install dependencies through pip.
   ```bash
   pip install -r requirements.txt
   ```

5. Go to [Tomorrow.io](https://www.tomorrow.io/), create an account and obtain an API key, then copy and paste your API key into the <api_key> variable in the widgets/GUIweather.py file on lines 16 and 55.

6. In the widgets/GUIweather.py file change the <location> variable on lines 19 and 58 to the desired city, state, and country. Additionally, you can change the <units> variable to "metric" if desired.

   Example on 19:
   ```python3
   location = "Mobile, AL, USA" # Location of weather
   ```

8. Again, in the widgets/GUIweather.py file go to line 102 and change the <image_path> variable to the accurate file path to the pictures foler.

   Example:
   ```python3
   image_path = "/Users/keg-macbook/MontyPython/raspi-dashboard/pictures/"
   ```

10. Go to the widgets/GUIgoogle.py, on lines 22, 29, 30, and 51 change the directory paths to reflect your full directory path to the credential folder.

    Example on line 22:
    ```python3
    credentials_file = '/Users/keg-macbook/MontyPython/Raspi-Dashboard/credentials/client_secret.json'
    ```
    Example on line 29:
    ```python3
    if os.path.exists('/Users/keg-macbook/MontyPython/raspi-dashboard-OG/credentials/token.json'):
    ```
    It is important to not change the file the directory path is leading to, so do not change the name of .json file you see, just the path leading to said file.

11. Go to https://console.cloud.google.com and make an account. Create and open a project called Google Calendar API, then navigate to the credentials tab. Follow the instructions to make an OAuth 2.0 Client ID. Download the .json file and run the following command from your downloads folder:
    ```bash
    cp *.json ~/Raspi-Dashboard/credentials/client_secret.json
    ```
    Otherwise, copy the contents of your newly downloaded .json file and paste it into the credentials/client_secret.json file.

12. Run the following commands from within the Raspi-Dashboard folder.
    ```bash
    python3 dashboard.py
    ```
