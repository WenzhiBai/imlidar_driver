# imlidar_driver
ROS imlidar Driver. This driver works to reading scans from the Inmotion's USB port.

��������lidar����,version: Beta v1.1��
����lidar�ͺţ�ILD26TRI
�� ubuntu1404LTS + ROS indigo �²���ͨ����

���룺
��neato_editĿ¼��ʹ��catkin_make������б��뼴�ɡ�

�״�ʹ�ã�
1����ILD26TRI����USB�ڣ���������ָ�����USB�ڵ�Ȩ�ޡ�
�����ʵ��ʹ�õĶ˿ںŵ�����USB_PORT��,(ʹ�� ls /dev ������Բ鿴�˿ں�)
sudo chmod 777 /dev/USB_PORT
2�������ն˻�����
�����ʵ�ʵ�Ŀ¼�޸ġ�PROJECT_DIRTORY���������ʵ�ʵ�shellѡ��.bash�����ļ�����.zsh���������͵������ļ�
source PROJECT_DIRTORY/neato_edit/devel/setup.bash
3������������
roslaunch inmotion_lidar_driver inmotion_lidar.launch
4����ros�з���һ����̬����ϵ�任��������rviz�й۲�lidar���ݡ���һ����Ϊ�˷�����rviz����ʾlidar�����ã�ʵ��ʹ��ʱ�������롣
rosrun tf static_transform_publisher 0 0 0 0 0 0 1 map inmotion_lidar_link 100
5������rviz�۲�lidar����Ч���������LaserScan���ݡ�
rosrun rviz rviz

���õ�����
��inmotion_lidar.launch��������Ը��ĸ������
port            �豸�˿ںţ�Ĭ��ֵ��/dev/ttyUSB0��
baud_rate       ���ڲ����ʣ�Ĭ��ֵ��115200���������������������
frame_id        lidar��������Ե�����ϵ���ƣ�Ĭ��ֵ��inmotion_lidar_link��
lidar_Hz        lidar����תƵ�ʣ�Ĭ��ֵΪ7����߿��Ե���Ϊ10Hz
angle_min	��С̽��Ƕȣ�Ĭ��ֵΪ��2*PI
angle_max	���̽��Ƕȣ�Ĭ��ֵΪ��0.0
angle_increment_direction �״�Ƕ���������Ĭ��ֵ�ǡ�cw������Ϊ˳ʱ�룬��ʱ�Ƕ�����Ϊ���������޸�Ϊ��ʱ�롰ccw�����Ƕ�����Ϊ�������ֵ���޸Ŀ��ܻᵼ��ROS�ж�λ�㷨�õ���Lidar�����ʵ�ʷ����෴������ͨ�����ð�װLidar������������⡣
