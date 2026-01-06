# RadioChat
A web app that enables one-way communication between ham radios and cell phones (or any other device with access to WiFi and an internet browser)
the app has a area to type a message, when you tap "send" the messege is sent to the radio in verbal speech
# Setup
First you will need a Raspberry Pi with the latest version of Raspberry Pi OS installed (prefferably desktop). I recomend a pi3B because that is what i used, and i can confirm it works, plus it is only $35 USD. I'm pretty sure a pi4B works too. I canot confirm a Raspberry Pi 5 will work, as many things were changed.
# Other materials
<list>
  <ul>3.5mm auxiliary cable (has headphone plug on both sides)</ul>
  <ul>decently loud speaker</ul>
  <ul>Keyboard mouse and monitor</ul>
  <ul>2 ham or GMRS radios with vox, preferably handheld, FRS walkie talkies will also work as long as you know what frequencies they operate on and they have vox</ul>
<list>
  
# Softwere installation
This is pretty straitforward. I uses espeak for this, which is a text to speach program available on Linuix.<br/>
open the terminal in Rasbperry pi OS and type the following commands.
```
sudo apt upgrade
sudo apt install espeak
```
one you've done that plug use the aux cable to connect the Pi to your speaker. then type the following command, you should hear the speaker say "hello" verbally
```
espeak "Hello"
```
Now you need to install flask. this is a python module that is used for hosting web pages. If this does not work and you see a messege like "Error: externally mannaged eviornment" you can google the prolem and find many solutions and other ways to install flask.
```
pip install flask
```

# Hosting the webpage on the Pi
put the file **radiochat.py** in this repository onto the Raspberry Pi filesystem and run it using the following command
```
python3 radiochat.py
```
note that if you put the file in a folder you will have to do
```
python3 <the_folder_you_put_the_file_in>/radiochat.py
```
if you cant figure out how to run it using the terminal, you can open it using a python IDE and press the run button.<br/>
if all goes well, you should see a messege in the terminal that says the IP adress hosing the page. On your cell phone go to that IP adress, for example "<your_pis_ip>:5000" in your browser.<br/>
This should take you to an interface with a box to type your message and a send button. Type a message and hit send
