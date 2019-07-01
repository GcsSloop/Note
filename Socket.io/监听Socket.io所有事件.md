# 监听 Socket IO 所有事件

**注意：适用于 NodeJs 的 socket.io**

以下事例已 vue 项目为例。

```javascript
import io from 'socket.io-client'

export default {
  	mounted() {
    	this.initWebSocket()
  	},
    initWebSocket() { // 初始化weosocket
      const socket = io.connect(window.apiUrl + ':9093/domain')
      let onevent = socket.onevent
      socket.onevent = function (packet) {
        let args = packet.data || []
        if (args === []) return
        onevent.call(this, packet)    // original call
        packet.data = ['*'].concat(args)
        onevent.call(this, packet)      // additional call to catch-all
      }

      socket.on('*', (event, data) => {
        // TODO 此处用来观测所有的 socket 接口
        console.log('socket.io * name = ' + event + ', data len = ' + JSON.stringify(data).length)
      })
    }
  }
}
```

