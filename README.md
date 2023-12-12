# webRTC
[音视频](https://juejin.cn/post/7068890609414570021?searchId=202312111741594CE3FEAC8CA849703E34)

只支持localhost和https协议

* 关闭webRTC
  ```
  function stopVideo(e) {
    showMsg("停止视频");
    const videoElem = document.querySelector('video');
    const stream = videoElem.srcObject;

    if(stream == null) {
        return;
    }
    const tracks = stream.getTracks();
  
    tracks.forEach(function(track) {
      track.stop();
    });
    videoElem.srcObject = null;
}

// 仅供参考

stream.getTracks()方法拿到所有的轨道（track），遍历一遍全部关掉。
最后，把videoElem.srcObject设置为null，它与前面的stream解除关联，方便将它释放

  ```
