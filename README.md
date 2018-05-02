Compiled fasushin's uhttpd files int file.bin and added a test html file and js file.



<code>>>> import uhttpd</code>
<code>>>> import uhttpd.file_handler</code>
<code>>>> server = uhttpd.Server([('/', uhttpd.file_handler.Handler('/www'))])</code>
<code>>>> server.run()</code>

