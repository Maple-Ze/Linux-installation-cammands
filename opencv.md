1. download Sources   https://opencv.org/releases/  opencv3

2. decompress

3. compile and install (take 3.4.14 as an example)

   ```
   cd opecv-3.4.14
   ```

   ```
   mkdir build
   ```

   ```
   cd build
   ```

   ```
   cmake -D CMAKE_BUILD_TYPE=Release -D CMAKE_INSTALL_PREFIX=/usr/local ..
   ```

   ```
   sudo make -j 16
   ```

   ```
   sudo make install
   ```

   ```
   sudo gedit /etc/ld.so.conf.d/opencv.conf
   ```

   add 

   /usr/local/lib

   ```
   sudo ldconfig
   ```

   ```
   sudo gedit /etc/bash.bashrc
   ```

   add   

   PKG_CONFIG_PATH=$PKG_CONFIG_PATH:/usr/local/lib/pkgconfig  

   export PKG_CONFIG_PATH

   ```
   source /etc/bash.bashrc
   ```

   ```
   sudo updatedb
   ```

4. test

   ```
   opencv-3.4.14/samples/cpp/example_cmake
   ```

   ```
   mkdir build
   ```

   ```
   cd build
   ```

   ```
   cmake ..
   ```

   ```
   make
   ```

   ```
   ./opencv_example
   ```

   The camera opens.