# ubuntu下指令汇总
## python指令
 - 创建虚拟环境```python3 -m venv venv ```
 - 激活虚拟环境```source venv/bin/activate```
 - 停止虚拟环境```deactivate```
##  systemd 启用和管理服务
 - 编辑自启动脚本```sudo nano /etc/systemd/system/my-python-app.service```
    
    样例 
    ```
    [Unit]
    Description=My Python App
    After=network.target
    [Service]
    Type=simple
    User=root
    Group=root
    WorkingDirectory=/opt/my_python_app/src
    ExecStart=/opt/my_python_app/venv/bin/python /opt/my_python_app/src/main.py
    Restart=always
    RestartSec=10
    StandardOutput=journal
    StandardError=journal
    [Install]
    WantedBy=multi-user.target
    ```
 - 重新加载 systemd 配置
    ```sudo systemctl daemon-reload```
 - 启用服务（开机自启）
    ```sudo systemctl enable my-python-app.service```
 - 启动服务
    ```sudo systemctl start my-python-app.service```
 - 检查服务状态
    ```sudo systemctl status my-python-app.service```
 - 查看服务日志
    ```sudo journalctl -u my-python-app.service -f```
 - 停止服务
    ```sudo systemctl stop my-python-app.service```
 - 禁用开机自启
   ```sudo systemctl disable my-python-app.service```
 - 查看最新的日志（实时跟踪）
   ```sudo journalctl -u my-python-app.service -f```
