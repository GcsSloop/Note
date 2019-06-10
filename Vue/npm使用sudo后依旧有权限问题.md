# npm EACCES: permission denied

碰到情况, 尝试使用sudo等管理员权限无效

```shell
gyp verb build dir attempting to create "build" dir: /Users/eddie/Desktop/GIT/hydra_frontend/src/m_v2/hb2018/node_modules/node-sass/build
gyp ERR! configure error 
gyp ERR! stack Error: EACCES: permission denied, mkdir '/Users/eddie/Desktop/GIT/hydra_frontend/src/m_v2/hb2018/node_modules/node-sass/build'
```

解决方案：

```shell
sudo npm install <package> --unsafe-perm=true --allow-root
```

