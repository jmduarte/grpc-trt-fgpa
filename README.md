
Install grpc
```
git clone https://github.com/grpc/grpc -b v1.27.0
cd grpc
git checkout -b v1.27.0
git submodule update --init
mkdir -p cmake/build
cd cmake/build
cmake ../..
make -j 8
sudo make install
```

Setup Vitis, XRT and paths to grpc
```
export PKG_CONFIG_PATH=/usr/local/lib/pkgconfig/
cd ../../examples/
git clone --recurse-submodules https://github.com/jmduarte/grpc-trt-fgpa -b alveo
cd grpc-trt-fgpa
make
./server hls4ml_c/xclbin/alveo_hls4ml.hw.xilinx_u250_xdma_201830_2.xclbin
```
