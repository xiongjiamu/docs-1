# 常见问题

## 手机USB连接个人电脑时使用usbManager.getDevices获取的设备列表为空

### 问题现象

手机通过USB方式与个人电脑连接后，在手机侧使用usbManager.getDevices获取设备列表为空，未将个人电脑识别为USB设备。

### 可能原因

USB设备包括主设备（Host）和从设备（Device）。主设备负责数据传输以及端口管理，从设备为被管理的对象。

usbManager.getDevices接口的作用，是在当前设备作为主设备时去获取所连接的从设备列表。

基于上述情况：

- 设备（如手机）USB连接个人电脑时，个人电脑默认是主设备，手机是从设备。
此时在手机侧调用usbManager.getDevices接口查询到设备列表为空，属于正常现象。
- 设备（如手机）USB连接鼠标键盘时，手机默认是主设备，鼠标键盘时从设备。
此时在手机侧调用usbManager.getDevices接口可以查询到设备列表。

### 解决措施

确保当前设备作为主设备，所连接的设备为从设备。（部分设备支持主、从两种USB设备模式。此时需要将设备设置为从设备模式，方可被主设备获取。）