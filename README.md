Built micropython firmware including fadushin's webserver module UHTTPD into file.bin to flash to an ESP8266. So many js libraries around to make super fun user interfaces for your hardware. I included smoothie.js in the file WWW to try out...

Flash the compiled versionn onto your ESP8266 using esptool.py

<code>esptool.py --port COM16 erase_flash</code>

<code>esptool.py --port COM16 --baud 460800 write_flash --flash_size=detect 0 C:/file.bin</code>

Then use ampy or webrepl to move the www folder and files onto your board: https://learn.adafruit.com/micropython-basics-load-files-and-run-code/file-operations

<code>ampy --port COM16 put C:/esp/www</code>

Finally you can use a serial monitor, webrepl, puTTy or the like to start typing python commands....

<code>>>> import uhttpd</code>

<code>>>> import uhttpd.file_handler</code>

<code>>>> server = uhttpd.Server([('/', uhttpd.file_handler.Handler('/www'))])</code>

<code>>>> server.run()</code>

