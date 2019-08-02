编译
make

实时检测
./darknet detector demo cfg/coco.data cfg/tiny-yolo.cfg weights/tiny-yolo.weights

./darknet detect cfg/yolov3.cfg weights/yolov3.weights data/dog.jpg
./darknet detect cfg/yolov3.cfg weights/yolov3.weights data/dog.jpg -thresh 0.5

./darknet detector test cfg/coco.data cfg/yolov3.cfg weights/yolov3.weights data/dog.jpg
./darknet detector demo cfg/coco.data cfg/yolov3.cfg weights/yolov3.weights [-thresh 0.5]
./darknet detector demo cfg/coco.data cfg/yolov3.cfg weights/yolov3.weights <video file>


问题1:
lvpchen@ubuntu-hy:~/workspace_lvpchen/darknet-org$ ./darknet detect cfg/yolov3.cfg weights/yolov3.weights data/dog.jpg
layer     filters    size              input                output
    0 CUDA Error: unknown error
darknet: ./src/cuda.c:36: check_error: Assertion `0' failed.
已放弃 (核心已转储)

原因：

解决方法：
先备份
sudo cp -r ~/.nv ~/.nv-back
删除
sudo rm -rf ~/.nv
