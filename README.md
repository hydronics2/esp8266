Compiled fasushin's uhttpd files into file.bin and added a test html file and js file. 

Flash the compiled versionn onto your ESP8266 using esptool.py
<code>esptool.py --port COM16 erase_flash</code>

<code>esptool.py --port COM16 --baud 460800 write_flash --flash_size=detect 0 C:/file.bin</code>



<code>>>> import uhttpd</code>

<code>>>> import uhttpd.file_handler</code>

<code>>>> server = uhttpd.Server([('/', uhttpd.file_handler.Handler('/www'))])</code>

<code>>>> server.run()</code>

