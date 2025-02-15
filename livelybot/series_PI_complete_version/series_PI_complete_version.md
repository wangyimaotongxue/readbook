# 量产串联PI整机版（orangepi）

### 小pi是由高擎机电推出的一款具有12自由度的小型双足机器人，支持二次开发，为开发者提供了一个性能优越且易于扩展的机器人平台。

- 操作系统：Ubuntu_20.04_desktop_arm
- ROS版本：ros-noetic-desktop
- 香橙派版本：Orangepi 5 Pro
  - 用户名(user name):orangepi  操作密码(password)：orangepi
- 鲁班猫版本：鲁班猫4
  - 用户名(user name):cat  操作密码(password)：temppwd
- Orin版本：Orin NX 16G
  - 用户名(user name):nvidia  操作密码(password)：nvidia
新版本小派分体机箱结构，逐步面向模块化，可以满足开发快拆。当前版本有如下注意事项：

# 开箱

## 物料检查:

![image](/livelybot/series_PI_complete_version/images/bill_of_materials.png "materials")

## 2. 配件清单:

| 说明 | 编号/名称 | 图例 | 数量 |
|-----|----------|:-----:|------|
| 必备 | 机器人整机 | ![image](/livelybot/series_PI_complete_version/images/robot_assembly.jpeg) | 1台 |
||电池| ![image](/livelybot/series_PI_complete_version/images/battery.png) | 1个 |
|必备| 充电仓 | ![image](/livelybot/series_PI_complete_version/images/charging_case.png) | 1个 |
|必备| 零位支架 | ![image](/livelybot/series_PI_complete_version/images/zero_position_calibration_bracket.png) | 1个 |
|必备|膝关节零位块| ![image](/livelybot/series_PI_complete_version/images/knee_joint_zero_position_calibration_block.png) |2个|
|必备|控制器| ![image](/livelybot/series_PI_complete_version/images/wireless_controller.png) |1个|
|必备|Type-C充电线| ![image](/livelybot/series_PI_complete_version/images/type-C_data_cable.png) |1根|
|必备|无线网卡（600Mbps）| ![image](/livelybot/series_PI_complete_version/images/wireless_network_card.png) |1个|
|必备|USB转CAN FD调试板| ![image](/livelybot/series_PI_complete_version/images/CANFD_debug_board.png) |1个|
|必备|XT 30 (2+2)线材| ![image](/livelybot/series_PI_complete_version/images/XT30(2+2)_data_cable.png) |1个|
|必备|EVA包装内胆| ![image](/livelybot/series_PI_complete_version/images/EVA_packaging_inlay.png) |1套|
|必备|包装纸箱| ![image](/livelybot/series_PI_complete_version/images/packaging_carton.png) |1套|
|必备|内六角扳手|  |2把|
|必备|拉杆行李箱|  |1个|

## 3. 机器人初始位姿与姿态矫正
### 3.1 机器人初始位姿说明：
![image](/livelybot/series_PI_complete_version/images/initial_pose.png) 
### 3.2 机器人姿态矫正：
- “零位支架”带标识箭头朝前；
- 将机器人按照上述四个步骤确认好使用前的位姿；
- 将机器人双腿分开适当角度后，将髋部两个电机置于“零位支架”上端，对齐后放入槽中；
![image](/livelybot/series_PI_complete_version/images/slight_leg_spread.png) 
注意：下图“零位支架”的“面1”与机器人的“面1”对应、“零位支架”的“面2”与机器人的“面2”对应，请参照下图示例；
![image](/livelybot/series_PI_complete_version/images/hip_joint_detail_1.png) 
![image](/livelybot/series_PI_complete_version/images/hip_joint_detail_2.jpeg) 
- 将机器人双腿向中间收拢，使脚掌前后及内侧贴紧“零位支架”下部槽中对应边；
![image](/livelybot/series_PI_complete_version/images/slight_leg_closure.png) 
![image](/livelybot/series_PI_complete_version/images/hip_joint_detail_3.png) 
- 将“膝关节零位块”下部槽口嵌入如图所示腿部零件，然后向上推，使得膝关节被锁紧。
![image](/livelybot/series_PI_complete_version/images/knee_joint_detail_1.png) 
# 4. 电池检查与充电
### 4.1 电池的使用和功能
![image](/livelybot/series_PI_complete_version/images/battery_switch.png) 
电池电源及功能：我们的电池适配了BMS电池管理系统，可对电池进行监控、过流保护、同时可以避免过充和过放的现象发生，电池上有状态指示灯及功能按键使用方法如下：
- 查看电池状态：在电池未启动时，短按电池一次即可显示当前电池电量（四个灯柱表示四个百分比）
- 启动电池：电池设有保护功能，要启动电池需要先短按一次后长按1秒以上再放开，当电量指示灯常亮则表示电池已正常开启；
- 关闭电池：要关闭电池也是同样的操作，先短按一次电源按键，随后长按电源按键大于1秒，电量指示灯熄灭即表示电池已经关闭。
### 4.2  电池充电与电池仓安装：
![image](/livelybot/series_PI_complete_version/images/battery_charging.png) 
按照（上面）图示方式安装电池到电池充电仓
安装方法：电池上有两个卡扣结构，同时用力夹紧两个卡扣，按上图所示方向插入充电仓，推到最深处让两个卡扣松开，使之锁紧到充电仓，即可将电池安装在充电仓中
### 4.3 充电：
- 将数据线和电源式配器（大于45W）正确连接后插入充电仓

- 进入充电模式：本产品电池采用BMS健康管理，需要将电池电源打开，随后BMS会自动识别工作状态进入充电模式
- 电池电量显示：电池上有4个灯柱，分别对应4个电量百分比，
  - 充电过程中灯柱会依次被点亮；
  - 充满电时电池自动断电，所有灯柱全部熄灭。

确认机器人外观无损坏后，你需要为机器人安装电池。我们的机器人在运输过程中，电池和机器人是分开放置的，你需要在航空箱中找到电池，并完成安装（请在第一次使用电池前先给电池充电）
### 4.4 机器人安装电池
- 安装电池：电池上有两个卡扣结构，同时用力夹紧两个卡扣，按下图所示方向插入电池仓，推到最深处让两个卡扣松开，使之锁紧到电池仓，即可将电池安装在机器人电池仓中
  
![image](/livelybot/series_PI_complete_version/images/battery_installation.png) 
  - 电池安装成功时会闪烁一次
- 取下电池：同样的，同时用力夹紧两个卡扣结构随后抽出电池即可取下（注意操作中电池要断电）
# 二、 机身接口详情
## 1. 背板接口
![image](/livelybot/series_PI_complete_version/images/back_panel_1.png) 
## 2. 香橙派外置接口
![image](/livelybot/series_PI_complete_version/images/Orange_Pi_interface.png) 
1. 预留了香橙派（Orangepi 5 Pro）HDMI 2.0接口
2. 千兆以太网口，支持PoE+（需要PoE+HAT）
3. USB 3.0 & USB 2.0 （蓝色标注的为USB 3.0接口，其他均为USB 2.0）
## 3. 开关和USB背板使用方法
找到USB外接板（USB设备内外切换按钮默认按下状态为内部主控系统工作）：

![image](/livelybot/series_PI_complete_version/images/USB_extension_board.png) 
### 3.1 USB外置接口调试板：
通信板的外置接口：左边的Type-C接口是通信板的外置接口
IMU的外置接口：右边的Type-C接口是IMU的外置接口
主控切换开关：白色按钮是内外部主控切换开关，当开关为按下锁紧状态为内部主控输入,当开关为松开弹起状态为外部系统输入。
### 3.2 机器人电源开关及功能
- 模组电源开关（Key 1）
  - 通电：短按下开关按钮即可打开关节模组电源，打开后开关灯光亮起
  - 断电：短按下开关按钮即可关闭关节模组电源，关闭后开关灯光熄灭
- 主控电脑（Key 2 ：Orangepi 5Pro或jetson nano Orin）电源按键及功能：
  - 通电：长按电源按键3秒以上随后放开即可，打开时开关灯光亮起
  - 断电：长按电源按键3秒以上随后放开即可，关闭后开关灯光熄灭
## 4. 状态显示屏
![image](/livelybot/series_PI_complete_version/images/status_display_screen_1.png) 
![image](/livelybot/series_PI_complete_version/images/status_display_screen_2.png) 
![image](/livelybot/series_PI_complete_version/images/status_display_screen_3.png) 
![image](/livelybot/series_PI_complete_version/images/status_display_screen_4.png) 
![image](/livelybot/series_PI_complete_version/images/status_display_screen_5.png) 
- 状态显示：
  - 关节状态显示：连接状态显示屏后，可实时检测关节状态，当发现某个关节模组信号丢失时，状态显示屏相对应位置的灯光会熄灭；一般的，个别关节状态信号灯熄灭则表示对应模组可能电源异常，若出现关节状态信号灯依次熄灭到末端。则表示该通道关节模组CAN信号丢失。
  - IUM数据打印：状态显示屏可以实现IMU数据打印，方便开发者更多的脱离外接显示器操作。
  - IP地址显示：分别打印回送地址（lo）、有线网络地址（eth0）、无线网络地址（wan0）在同一个页面
  - 电池电量显示：该页面可实时查看电池电量信息
  - 机器人模式管理：该页面可以选择对应的机器人控制模式
- 摇杆开关：
  - 左右拨摇杆开关可依次实现IMU信息、关节状态显示、IP地址、机器人节点管理、电量显示等功能的切换的切换
# 三、 操作方法

| 操作步骤 | 操作示例 | 操作说明 |
|---|---|---|
| 校对关节 | ![image](/livelybot/series_PI_complete_version/images/hip_joint_detail_3.png) | 该操作请将姿位调至正确状态，并将机器人放置零位支架上|
插入遥控器手柄的无线接收器| ![image](/livelybot/series_PI_complete_version/images/insert_controller_wireless_receiver%20.png) | 在机器人开机前，将遥控器手柄的无线接收器插入机器人外置的任意USB 2.0接口上 |
| 开机 | ![image](/livelybot/series_PI_complete_version/images/module_switch.png) ![image](/livelybot/series_PI_complete_version/images/main_control_switch.png) | 短按关节模组开关，红色指示灯亮起即可\长按3s启动主控系统开关，红色指示灯亮起（约20s后即可配对手柄）|
| 手柄配对 | ![image](/livelybot/series_PI_complete_version/images/controller_START_button.png) | 给机器人上电后，大约20s后按下手柄开始（START）按键 \ 配对完成：当手柄会震动片刻同时侧边LED亮起，则表示配对成功 |
| 切换状态显示屏 ![image](/livelybot/series_PI_complete_version/images/switch_status_display_screen.png) | ![image](/livelybot/series_PI_complete_version/images/back_panel_2.png) ![image](/livelybot/series_PI_complete_version/images/next_step.png) ![image](/livelybot/series_PI_complete_version/images/status_display_screen_5.png) | 等待系统启动：系统完全启动后状态显示屏会有关节连接信息显示 \切换状态显示：按照箭头方向，向左或向右任意方向拨动摇杆，即可切换状态显示，请切换状态显示至Robot_State页面 |


机器人运动测试注意事项：在确认启动机器人前，请将机器人从零位支架上移出，并使机器人半蹲在空旷地面上

![image](/livelybot/series_PI_complete_version/images/squatting.png)

运控操作方式请参照表：四-1

控制模式选择：四-2
|-|-|-|
|---|---|---|
|关机（请尽量避免热关机） | ![image](/livelybot/series_PI_complete_version/images/status_display_screen_5.png) | 完成上述操作后，您可进行关机操作，确保已结束对机器人的控制，节点管理显示为INITIAL(初始状态)随后短按模组电源，长按主控电源键，等待上述LED灯熄灭，随后短按长按关闭电池 |

# 四、 运动控制测试
### 1. 无线控制器按键及功能
无线控制器的使用：按键请参考手柄图示
![image](/livelybot/series_PI_complete_version/images/wireless_controller_button_side.png)
![image](/livelybot/series_PI_complete_version/images/wireless_controller_trigger_side.jpg)
- 控制模式选择：选择模式需要左右扳机同时按下（LT + RT）并保持
  - 模式切换：保持（LT+RT）按下，随后按下【十字方向键（左 or 右）（Left or Right）】可进行切换不同的控制模式
  - 模式选中：保持（LT+RT）按下，随后按下（A）键即可选中当前控制模式
  - 退出模式：保持（LT+RT）按下，随后按下（B）键即可退出当前控制模式

- 基本按键操作说明：
  - 启动机器人：按下左摇杆垂直（LS ⊥），机器人会站立起来（为了确保功能正常，请事先将机器人提起）
  - 行走与停止：按下LB时机器人可以自行前进，再次按下即可暂停
  - 前后移动：左摇杆（LS），上推摇杆时机器人前进，下推摇杆时机器人后退
  - 左右平移：左摇杆（LS），左推摇杆时机器人向左平移，右推摇杆时机器人向右平移
  - 转向与偏航：右摇杆（RS），左推摇杆时机器人向左偏航，右推摇杆时机器人向右偏航
  - 结束控制：按下RB时机器人将停止接受遥控器的控制（关闭控制时，请勿将手指等靠近机器人，注意安全，当心夹手）
  - 动作加速：按下（LT）配合俯仰和偏航即可实现运动加速
- 调节机器人体位：
  - 髋关节（减）：按下（A）可调节髋关节前倾
  - 髋关节（加）：按下（Y）可调节乱关节后仰
  - 膝关节（减）：按下（X）可调节膝关节前倾
  - 膝关节（加）：按下（B）可调节膝关节后仰
  - 踝关节（减）：按下（View button）可调节踝关节前倾
  - 踝关节（加）：按下（Menu button）可调节踝关节后仰
  注意：调节体位状态时应尽量使机器人关节并垂直排列

| 遥控器 | 状态展示 | 控制方法|
|---|---|---|
| ![image](/livelybot/series_PI_complete_version/images/trigger_LT_and_RT.png) ![image](/livelybot/series_PI_complete_version/images/directional_pad_left_right.png) | ![image](/livelybot/series_PI_complete_version/images/INITIAL_panel.png) ![image](/livelybot/series_PI_complete_version/images/next_step.png) ![image](/livelybot/series_PI_complete_version/images/DEFAULT_preselection_panel.png) | 模式切换：保持（LT+RT）按下，随后按下【十字方向键（左 or 右）（Left or Right）】可进行切换不同的控制模式 |
| ![image](/livelybot/series_PI_complete_version/images/trigger_LT_and_RT.png) ![image](/livelybot/series_PI_complete_version/images/button_A_or_B.png) | ![image](/livelybot/series_PI_complete_version/images/DEFAULT_preselection_panel.png) ![image](/livelybot/series_PI_complete_version/images/next_step.png) ![image](/livelybot/series_PI_complete_version/images/DEFAULT_panel.png) | 模式选中：保持（LT+RT）按下，随后按下（A）键即可选中当前控制模式 \ 退出模式：保持（LT+RT）按下，随后按下（B）键即可退出当前控制模式 |
| ![image](/livelybot/series_PI_complete_version/images/left_joystick_down.png) | ![image](/livelybot/series_PI_complete_version/images/stand_up.png) | 左摇杆（LS ⊥），按下即可使机器人缓慢站起
| ![image](/livelybot/series_PI_complete_version/images/button_LT.png) | ![image](/livelybot/series_PI_complete_version/images/marching.png) ![image](/livelybot/series_PI_complete_version/images/standing.png) | 踏步与停止：按下LB时机器人可以原地踏步，再次按下即可暂停 | 
| ![image](/livelybot/series_PI_complete_version/images/joystick_pitch.png) | ![image](/livelybot/series_PI_complete_version/images/pitch.png) | 左摇杆（LS），上推摇杆时机器人前进 \ 左摇杆（LS），下推摇杆时机器人后退 | 
| ![image](/livelybot/series_PI_complete_version/images/joystick_roll.png) | ![image](/livelybot/series_PI_complete_version/images/roll.png) | 左摇杆（LS），左推摇杆时机器人向左平移 \ 左摇杆（LS），右推摇杆时机器人向右平移 |
| ![image](/livelybot/series_PI_complete_version/images/joystick_yaw.jpeg) | ![image](/livelybot/series_PI_complete_version/images/yaw.jpeg) | 右摇杆（RS），左推摇杆时机器人向左偏航 \ 右摇杆（RS），右推摇杆时机器人向右偏航 |
| ![image](/livelybot/series_PI_complete_version/images/button_RT.png) |![image](/livelybot/series_PI_complete_version/images/squat_down.png) | 结束控制：按下RB时机器人将停止接受遥控器的控制（关闭控制时，请勿将手指等靠近机器人，注意安全，当心夹手）|

## 2. 控制模式
| 控制模式节点管理| 背板屏幕状态显示 | 节点说明|
|---|---|---|
| 初始状态 | ![image](/livelybot/series_PI_complete_version/images/INTIAL.png) |机器人管理节点启动，但并不会有任何触发动作。|
| 默认状态 | ![image](/livelybot/series_PI_complete_version/images/DEFAULT.png) | 原有的sim2real操作逻辑，在sim2real内部按键关闭或触发限位关闭，视为正常关闭，跳转到init状态。\ 如果是检测imu和电机出问题，进入保护模式。\ 或主动关闭控制状态，也进入阻尼模式。| 
| 自定义状态 | ![image](/livelybot/series_PI_complete_version/images/CUSTUM.png) | 和默认模式完全一致，但是提供config文件接口，可以自己修改policy和其他参数，但是更换的policy尽可能使用我们的开源训练算法训练。\（如果不用我们的算法，起码要保证要和我们的policy的出口和入口长度一致。）|
| 遥控状态 | ![image](/livelybot/series_PI_complete_version/images/REMOTE.png) | 在小派，不断订阅主机发布的jointstate话题，并且不断执行。\ 在主机，获得小派的关节状态和imu状态的可视化，并且不断发布jointstate给小派 |
| 保护状态| ![image](/livelybot/series_PI_complete_version/images/PROTRCT.png) | 当imu或关节有问题时，或在其他的运动模式阶段主动中断模式时，进入这个模式，再次按主动中断，电机没有任何控制 |
| 错误状态 | ![image](/livelybot/series_PI_complete_version/images/ERROR.png) | 当机器人检测到有电机未连接等情况时，会显示错误状态。需要检查关节通信正常后稍等片刻自动恢复 |

到这里，相信您已经掌握了强化学习控制程序的基本使用方法，您可以尽情的驾驭您的机器人了，感谢对高擎机电产品的支持，祝您工作愉快！