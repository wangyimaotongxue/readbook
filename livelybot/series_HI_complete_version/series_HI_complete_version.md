小Hi是由高擎机电推出的一款具有23自由度的小型人形机器人，支持二次开发，为开发者提供了一个性能优越且易于扩展的机器人平台。
- 操作系统：Ubuntu_20.04_desktop_arm
- ROS版本：ros-noetic-desktop
- NUC版本：雷神MIX 13620H000
  - 用户名(user name):livelybot  操作密码(password):["  "(两个空字符)]
- Jeston 版本：Orin_NX 16G moud
  - 用户名(user name):nvidia  操作密码(password):nvidia

# 一、开箱
## 物料检查
## 1.  装箱分类框图：
![image](/livelybot/series_HI_complete_version/p1/HI_bill_of_materials.png)
## 2. 配件清单：
| 说明 | 编号/名称 | 图例 | 数量 | 
|---|---|---|---|
必配 | 机器人整机 | ![image](/livelybot/series_HI_complete_version/p1/robot_assembly.png) | 1台 |
| | 电池 | ![image](/livelybot/series_HI_complete_version/p1/battery.png) | 1个 |
| | 充电仓 | ![image](/livelybot/series_HI_complete_version/p1/charging_case.png) |1个 |
| | 零位支架 | ![image](/livelybot/series_HI_complete_version/p1/zero_position_calibration_bracket.png) | 1个 |
| | 膝关节零位块 | ![image](/livelybot/series_HI_complete_version/p1/knee_joint_zero_position_calibration_block.png) |2个 |
| | 控制器 | ![image](/livelybot/series_HI_complete_version/p1/wireless_controller.png) | 1个 |
| | Type-C充电线 | ![image](/livelybot/series_HI_complete_version/p1/type-C_data_cable.png) | 1根 |
| | 无线网卡(600Mbps) | ![image](/livelybot/series_HI_complete_version/p1/wireless_network_card.png) | 1个 | 
| | USB转CAN FD调试板 | ![image](/livelybot/series_HI_complete_version/p1/CANFD_debug_board.png) | 1个 |
| | XT 30 (2+2)线材 | ![image](/livelybot/series_HI_complete_version/p1/XT30(2+2)_data_cable.png) | 2根 | 
| | 内六角扳手 | ![image](/livelybot/series_HI_complete_version/p1/hex_key_screwdriver.png) | 1套 | 
| | 拉杆行李箱 | ![image](/livelybot/series_HI_complete_version/p1/trolley_suitcase.png) | 1个 |
| | 安全挂绳 | ![image](/livelybot/series_HI_complete_version/p1/safety_lanyard.png) | 1根 | 

## 3. 机器人初始位姿与姿态矫正
### 3.1 机器人初始位姿说明
![image](/livelybot/series_HI_complete_version/p1/INITIAL_pose.png)

### 3.2 末端零位支架安装步骤
1.把图示肘关节逆时针旋转90°
![image](/livelybot/series_HI_complete_version/p1/joint_zero_position_detail_0.png)
![image](/livelybot/series_HI_complete_version/p1/joint_zero_position_detail_1.png)

2.将末端零位支架装入下图图示位置
![image](/livelybot/series_HI_complete_version/p1/joint_zero_position_detail_2.png)
![image](/livelybot/series_HI_complete_version/p1/joint_zero_position_detail_3.png)

3.按以上步骤安装另一个零位支架即可

### 3.3 机器人姿态矫正：
- “零位支架”带标识箭头朝前；
- 将机器人按照上述四个步骤确认好使用前的位姿；
- 将机器人双腿分开适当角度后，将髋部两个电机置于“零位支架”上端，对齐后放入槽中；

![image](/livelybot/series_HI_complete_version/p1/joint_zero_position_detail_4.png)

注意：下图“零位支架”的“面1”与机器人的“面1”对应、“零位支架”的“面2”与机器人的“面2”对应，请参照下图示例；

![image](/livelybot/series_HI_complete_version/p1/joint_zero_position_detail_5.png)

- 将机器人双腿向中间收拢，使脚掌前后及内侧贴紧“零位支架”下部槽中对应边；
![image](/livelybot/series_HI_complete_version/p1/joint_zero_position_detail_6.png)

![image](/livelybot/series_HI_complete_version/p1/joint_zero_position_detail_7.png)

- 膝关节零位支架使用方法
注意：下图“膝关节零位支架”的“面1”与机器人的“面1”对应、“膝关节零位支架”的“面2”与机器人的“面2”对应，请参照下图示例；

![image](/livelybot/series_HI_complete_version/p1/joint_zero_position_detail_8.png)
![image](/livelybot/series_HI_complete_version/p1/joint_zero_position_detail_9.png)

## 4. 电池检查与充电
### 4.1 电池的使用和功能
![image](/livelybot/series_HI_complete_version/p1/battery_switch.png)

电池电源及功能：我们的电池适配了BMS电池管理系统，可对电池进行监控、过流保护、同时可以避免过充和过放的现象发生，电池上有状态指示灯及功能按键使用方法如下：
- 查看电池状态：在电池未启动时，短按电池一次即可显示当前电池电量（四个灯柱表示四个百分比）
- 启动电池：电池设有保护功能，要启动电池需要先短按一次后长按1秒以上再放开，当电量指示灯常亮则表示电池已正常开启；
- 关闭电池：要关闭电池也是同样的操作，先短按一次电源按键，随后长按电源按键大于1秒，电量指示灯熄灭即表示电池已经关闭。
### 4.2  电池充电与电池仓安装：
![image](/livelybot/series_HI_complete_version/p1/battery_charging.png)

按照上图所示方式安装电池到电池充电仓
安装方法：电池上有两个卡扣结构，同时用力夹紧两个卡扣，按上图所示方向插入充电仓，推到最深处让两个卡扣松开，使之锁紧到充电仓，即可将电池安装在充电仓中。
### 4.3 充电：
- 将数据线和电源式配器（大于45W）正确连接后插入充电仓。
- 进入充电模式：本产品电池采用BMS健康管理，需要将电池电源打开，随后BMS会自动识别工作状态进入充电模式。
- 电池电量显示：电池上有4个灯柱，分别对应4个电量百分比（25%/50%/75%/100%）。
  - 充电过程中灯柱会依次被点亮；
  - 充满电时电池自动断电，所有灯柱全部熄灭。

确认机器人外观无损坏后，你需要为机器人安装电池。我们的机器人在运输过程中，电池和机器人是分开放置的，你需要在航空箱中找到电池，并完成安装（注意：电池首次使用前请先给电池充电）。
### 4.4 机器人安装电池
- 安装电池：电池上有两个卡扣结构，同时用力夹紧两个卡扣，按下图所示方向插入电池仓，推到最深处让两个卡扣松开，使之锁紧到电池仓，即可将电池安装在机器人电池仓中。电池安装成功时会闪烁一次。
  
![image](/livelybot/series_HI_complete_version/p1/battery_installation.png)

- 取下电池：同样的，同时用力夹紧两个卡扣结构随后抽出电池即可取下（注意操作中电池要断电）。
# 二、 机身接口详情
## 1. 背板接口
![image](/livelybot/series_HI_complete_version/p2/back_panel.png)
## 2. 主控外置接口(NUC)
![image](/livelybot/series_HI_complete_version/p2/NUC_interface.png)

1. 预留了2个HDMI 2.0接口
2. 千兆以太网口
3. USB 3.2
4. USB 2.0 
5. 两个雷电接口
## 3. 开关和USB背板使用方法
找到USB外接板（默认为按下状态：内部主控系统工作）：
![image](/livelybot/series_HI_complete_version/p2/USB_extension_board.png)

### 3.1 USB外置接口调试板
通信板的外置接口：左边的Type-C接口是通信板的外置接口
IMU的外置接口：右边的Type-C接口是IMU的外置接口
主控切换开关：白色按钮是内外部主控切换开关，当开关为按下锁紧状态为内部主控输入，当开关为松开弹起状态为外部系统输入。
### 3.2 机器人电源开关及功能
- 模组电源开关（Key 1）
  - 通电：短按下开关按钮即可打开关节模组电源，打开后开关灯光亮起
  - 断电：短按下开关按钮即可关闭关节模组电源，关闭后开关灯光熄灭
- 主控电脑（Key 2 ：Orangepi 5Pro或jetson nano Orin）电源按键及功能：
  - 通电：长按电源按键1秒以上随后放开即可，打开时开关灯光亮起
  - 断电：长按电源按键1秒以上随后放开即可，关闭后开关灯光熄灭
## 4. 状态显示屏
![image](/livelybot/series_HI_complete_version/p2/status_display_screen_0.png)
![image](/livelybot/series_HI_complete_version/p2/status_display_screen_2.png)
![image](/livelybot/series_HI_complete_version/p2/status_display_screen_3.png)
![image](/livelybot/series_HI_complete_version/p2/status_display_screen_4.png)
- 状态显示：
  - 关节状态显示：连接状态显示屏后，可实时检测关节状态，当发现某个关节模组信号丢失时，状态显示屏相对应位置的灯光会熄灭；一般的，个别关节状态信号灯熄灭则表示对应模组可能电源异常，若出现关节状态信号灯依次熄灭到末端。则表示该通道关节模组CAN信号丢失。
  - IUM数据打印：状态显示屏可以实现IMU数据打印，方便开发者更多的脱离外接显示器操作。
  - IP地址显示：分别打印回送地址（lo）、有线网络地址（eth0）、无线网络地址（wan0）在同一个页面
  - 电池电量显示：该页面可实时查看电池电量信息
  - 机器人模式管理：该页面可以选择对应的机器人控制模式
- 摇杆开关：
  - 左右拨摇杆开关可依次实现IMU信息、关节状态显示、IP地址、机器人节点管理、电量显示等功能的切换的切换

# 三、 操作方法

## 1. 启动机器人

| 操作步骤 | 操作示例 | 操作说明 |
|---|---|---|
| 校对关节 | ![image](/livelybot/series_HI_complete_version/p3/joint_position_detail.png) | 该操作请将姿位调至正确状态，并将机器人放置零位支架上
| 插入遥控器手柄的无线接收器 | ![image](/livelybot/series_HI_complete_version/p3/insert_controller_wireless_receiver%20.png) | 在机器人开机前，将遥控器手柄的无线接收器插入机器人外置的USB 2.0接口上 |
| 开机 | ![image](/livelybot/series_HI_complete_version/p3/module_switch.png) ![image](/livelybot/series_HI_complete_version/p3/main_control_switch.png) | 短按关节模组开关，红色指示灯亮起即可 \ 长按1s启动主控系统开关，红色指示灯亮起（约20s后即可配对手柄） | 
| 手柄配对 | ![image](/livelybot/series_HI_complete_version/p3/controller_START_button.png) | 给机器人上电后，大约20s后按下手柄开始（START）按键 \ 配对完成：当手柄会震动片刻同时侧边LED亮起，则表示配对成功 |
| 切换状态显示屏 ![image](/livelybot/series_HI_complete_version/p3/status_display_screen_0.png) | | 等待系统启动：系统完全启动后状态显示屏会有关节连接信息显示 \ 切换状态显示：按照箭头方向，向左或向右任意方向拨动摇杆，即可切换状态显示，请切换状态显示至Robot_State页面。|
| 关机 | ![image](/livelybot/series_HI_complete_version/p3/main_control_switch.png) ![image](/livelybot/series_HI_complete_version/p3/module_switch.png) | 在关机前请确保已结束对机器人的控制。使模式管理显示为INITIAL（初始状态）随后短按模组电源，长按主控电源键，等待上述电源LED灯熄灭，随后短按长按关闭电池（注意：请尽量避免热关机）。 |

## 2. 连接从机 并打开相机节点

```bash
#使用SSH链接从机（已配置好，IP：192.168.10.101）
ssh nvidia@192.168.10.101

#启用视觉
ls
cd catkin
source ./devel/setup.bash
roslaunch realsense2_camera rs_camera.launch
#如果错误提示为找不到主机相关的信息，请在主机端开启一个新终端并执行'roscore'
```

- 在主机端新开终端并查看话题

```bash
rostopic list
```

- 使用本Riz检查相机传感器状态
```bashrc
rviz
```

## 3. 启动MPC
```bash
#给所有的设备赋权限
sudo chmod -R 777 /dev/tty*
#添加环境
source ./devel/setup.bash
#启动仿真程序roslaunch hi_controllers one_s8tart_gazebo.launch
roslaunch hi_controllers one_start_gazebo.launch
#启动机器人
roslaunch hi_controllers one_start_real.launch 
```

# 四、 运动控制测试
机器人运动测试注意事项：在确认启动机器人前，请先将机器人从零位支架上移出，并吊起，随后调节PID等相关参数。
1. 无线控制器按键及功能
![image](/livelybot/series_HI_complete_version/p4/wireless_controller_button_side.png)

按键请参考手柄图示
- 基本按键操作说明：
  - 复位：按下（A），可使机器人复位
  - 行走：按下（LB）时机器人可以原地踏步
  - 前后移动：左摇杆（LS），上推摇杆时机器人前进，下推摇杆时机器人后退
  - 转向与偏航：右摇杆（RS），左推摇杆时机器人向左偏航，右推摇杆时机器人向右偏航
  - 急停：按下菜单键[(more) or ("+" of 奥佳狮)]（关闭控制时，请勿将手指等靠近机器人，注意安全，当心夹手）

| 遥控器 | 状态展示 | 控制方法 |
|---|---|---|
| ![image](/livelybot/series_HI_complete_version/p4/button_A.png) | ![image](/livelybot/series_HI_complete_version/p4/Rviz.png) | 复位：按下A键使机器人复位，此时可以看到机器人在RVIZ中会重新将模型加载到坐标原点 | 
| ![image](/livelybot/series_HI_complete_version/p4/button_LT.png) | ![image](/livelybot/series_HI_complete_version/p4/marching.png) ![image](/livelybot/series_HI_complete_version/p4/standing.png) | 行走：按下LB时机器人可以原地踏步，再次按下即可暂停 |
| ![image](/livelybot/series_HI_complete_version/p4/view_view.png) | ![image](/livelybot/series_HI_complete_version/p4/stop.png) | 急停：按下菜单键[(more) or ("+" of 奥佳狮)] 。\ 注意：当前机器人只有急停按键可作为停止按键使用。急停按键按下时，机器人会全身泄力并倒地，请在急停前将机器人挂起或用手搀扶，若机器人失控，请尽可能的远离机器人并迅速按下急停。| 
| ![image](/livelybot/series_HI_complete_version/p4/joystick_pitch.png) | ![image](/livelybot/series_HI_complete_version/p4/pitch.png) | 左摇杆（LS），上推摇杆时机器人前进 \ 左摇杆（LS），下推摇杆时机器人后退 | 
| ![image](/livelybot/series_HI_complete_version/p4/joystick_yaw.jpeg) | ![image](/livelybot/series_HI_complete_version/p4/yaw.png) | 右摇杆（RS），左推摇杆时机器人向左偏航 \ 右摇杆（RS），右推摇杆时机器人向右偏航 | 

2. 调节PID

![image](/livelybot/series_HI_complete_version/p4/Refresh.png)
![image](/livelybot/series_HI_complete_version/p4/control_PID.png)
![image](/livelybot/series_HI_complete_version/p4/information.png)
![image](/livelybot/series_HI_complete_version/p4/stand_up.png)

到这里，相信您已经掌握了MPC+WBC控制程序的基本使用方法，您可以尽情地驾驭您的机器人了，感谢您对高擎机电产品的支持，祝您工作愉快！
