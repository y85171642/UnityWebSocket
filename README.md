
[(English)](README_EN.md)

<div align=center>
  <img src="https://s1.ax1x.com/2020/08/21/dYIAQU.png" width=20%/>
</div>

## **在线示例**

- **[https://psygames.github.io/UnityWebSocket/](https://psygames.github.io/UnityWebSocket/)**


## **快速开始**

### **安装方法**

  - 在 [Releases](https://github.com/psygames/UnityWebSocket/releases) 页面中，下载最新版本的 `UnityWebSocket.unitypackage` 安装包，然后导入到您的项目中。


### **使用方法**

- 代码示例

  ```csharp
  // 命名空间
  using UnityWebSocket;

  // 创建实例
  string address = "ws://echo.websocket.org";
  WebSocket socket = new WebSocket(address);

  // 注册回调
  socket.OnOpen += OnOpen;
  socket.OnClose += OnClose;
  socket.OnMessage += OnMessage;
  socket.OnError += OnError;

  // 连接
  socket.ConnectAsync();

  // 发送 string 类型数据
  socket.SendAsync(str); 

  // 或者 发送 byte[] 类型数据（建议使用）
  socket.SendAsync(bytes); 

  // 关闭连接
  socket.CloseAsync();
  ```

- 更多使用方法可参考项目中的 [UnityWebSocketDemo.cs](Assets/UnityWebSocket/Demo/UnityWebSocketDemo.cs) 示例代码。

- 可添加 Unity 编译宏：
  - `UNITY_WEB_SOCKET_LOG` 打开底层日志输出。
  - `UNITY_WEB_SOCKET_SHARP` 使用 [websocket-sharp](https://github.com/sta/websocket-sharp) 插件。
  - `UNITY_WEB_SOCKET_NINJA` 使用 [Ninja.WebSockets](https://github.com/ninjasource/Ninja.WebSockets) 插件。


### **注意（Warning）**

- 插件中多个命名空间中存在 **WebSocket** 类，适用不同环境，请根据自身需求选择。

  命名空间 | 平台 | 方式 |  说明  
  -|-|-|-
  UnityWebSocket | 全平台 | 同步(无阻塞) | **[推荐]** 无需考虑异步回调使用 Unity 组件的问题。
  UnityWebSocket.Uniform | 全平台 | 异步 | 需要考虑异步回调使用 Unity 组件的问题。
  UnityWebSocket.WebGL | WebGL平台 | 异步 | 仅支持WebGL平台下的通信。
  UnityWebSocket.NoWebGL | 非WebGL平台 | 异步  | 仅支持非WebGL平台下的通信。

### **QQ 交流群**
- 1126457634 >>> [入群通道](https://qm.qq.com/cgi-bin/qm/qr?k=KcexYJ9aYwogFXbj2aN0XHH5b2G7ICmd) <<<
