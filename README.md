Compiled fasushin's uhttpd files int file.bin and added a test html file and js file.




>>> import uhttpd
>>> import uhttpd.file_handler
>>> server = uhttpd.Server([('/', uhttpd.file_handler.Handler('/www'))])
>>> server.run()
