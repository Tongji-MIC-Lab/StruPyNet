Instructions:

#### Testing (Inference)

1. Please download the code from https://github.com/xmfbit/flownet2 or https://github.com/lmb-freiburg/flownet2 and follow the instructions there to compile the code.
2. Put warp_layer.cu and warp_layer.cpp (in ./warping_code) to src/caffe/layers and warp_layer.hpp (in ./warping_code) to include/caffe/layers, recompile.
3. Run python ./proc_images.py [img1.txt img2.txt out.txt]. Please compare your results with ./tmp/reference_frame_0010_forward.flo and ./tmp/reference_frame_0011_backward.flo.

The program assumes that images to process are of the same size.


#### Benchmarking time

Please modify the caffe directory below and set parameters $WIDTH and $HEIGHT in time_benchmarking.prototxt to the size of the image pair you input.

YOUR_DIRECTORY/flownet2/build/tools/caffe.bin time -model ./benchmark_time/time_benchmarking.prototxt -weights ./model/StruPyNet.caffemodel -iterations 100 -gpu 0;


#### Training 

1.Please download the FlyingChairs dataset from https://lmb.informatik.uni-freiburg.de/resources/datasets, make the LMDB file, modify the local directory in ./model/train.prototxt. 
2.Modify the local directory in  ./train.py and Run ./train.py
