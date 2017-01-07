# imlidar_driver
## Purpose
ROS imlidar Driver. This driver works to reading scans from the serial port.

## Version
ROS imlidar Driver version: Beta v0.2.0  
����lidar�ͺţ�ILD26TRI  
�� ubuntu14.04 + ROS indigo �²���ͨ��

## Getting started
1. ��������ʼ�������ռ�  
`mkdir catkin_ws`  
`cd catkin_ws`  
`wstool init src`  
2. ��ȡԴ��  
`cd src`  
`git clone https://github.com/wenhust/imlidar_driver.git`  
3. ����  
`catkin_make ..`  
4. �����ն˻���  
`echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc`  
`source ~/.bashrc`  

#### �״�ʹ��
1. ����ROS  
`roscore`  
2. ����imlidar  
`rosrun imlidar_driver imlidar_node`  
���ߣ��������ò�����ʹ�ã�  
`roslaunch imlidar_driver imlidar.launch`  
�����ʾ�򿪶˿�ʧ�ܣ�������Ƕ˿ڲ���Ȩ�޲�����  
`ls -l /dev/ttyUSB0`  
����ʾΪcrw-rw----����Ϊ���Ȩ��ʹ����ʾΪcrw-rw-rw-  
`sudo chmod a+rw /dev/ttyUSB0`  
ʹ�� ls /dev ������Բ鿴�˿ںţ��˴�ʾ���˿ں�ΪttyUSB0
3. ����view_imlidar.launch  
`roslaunch imlidar_driver view_imlidar.launch`  
���ű������rviz�й۲������Ƿ���ȷ

#### ��������  
ʹ��gedit��imlidar.launch��������Ը��ĸ������  
port:�豸�˿ںţ�Ĭ��ֵ��/dev/ttyUSB0��
baud_rate:���ڲ����ʣ�Ĭ��ֵ��115200���������������������
frame_id:lidar��������Ե�����ϵ���ƣ�Ĭ��ֵ��imlidar��
rps:��תƵ�ʣ�Ĭ��ֵΪ7Hz����߿��Ե���Ϊ10Hz
data_sequence_direction:�״�Ƕ���������Ĭ��ֵ�ǡ�cw������Ϊ˳ʱ�룬��ʱ�Ƕ�����Ϊ���������޸�Ϊ��ʱ�롰ccw�����Ƕ�����Ϊ�������ֵ���޸Ŀ��ܻᵼ��ROS�ж�λ�㷨�õ���Lidar�����ʵ�ʷ����෴������ͨ�����ð�װLidar������������⡣|
