## Example of a web server using Pico SDK and lwIP
This example was described in more detail in a blog post: https://krzmaz.github.io/2022-08-15-creating-a-web-server-on-raspberry-pi-pico-w-using-pico-sdk-and-lwip/  
In my testing it reached ~20x performance of the MicroPython implementation from point 3.9.1 of https://datasheets.raspberrypi.com/picow/connecting-to-the-internet-with-pico-w.pdf

If you want to test this example with your html files, just add/edit them in the `src/fs` directory and rebuild the project! 

---
**NOTE**

This project was only tested on Linux and MacOS, I haven't prepared it for Windows.  
If you need that, feel free to contribute a PR or reach out in the issue section!

---

### One time setup
```bash
cp cmake/credentials.cmake.example cmake/credentials.cmake
# <fill in your credentials>
```
### Building
```bash
./build.sh
```

### Flashing
The built USB Flashing Format file will be located in `build/src/pico_w_webserver.uf2` - just copy it over to the Pico W to flash it!

### SSI
Now the example uses Server Side Includes (SSI) to introduce dynamic data into the HTML responses.  
As per documentation:
> SSI-enabled pages must have one of the predefined SSI-enabled file extensions

Which means that no cost should be introduced in non SSI pages
### References
- https://www.nongnu.org/lwip/2_1_x/group__httpd.html
- https://github.com/lwip-tcpip/lwip/tree/master/contrib/examples/httpd
