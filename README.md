一、确保环境
torch2.7.1，CUDA12.8，triton3.2
建议按照这个标准来，版本号都保持不变
二、更改CUDA
CUDA把以前的删了，然后去安装
进入https://developer.nvidia.com/cuda-toolkit  然后在页面中选择Download Now
<img width="1338" height="632" alt="image" src="https://github.com/user-attachments/assets/35eee477-23b5-43b6-88fd-e1c1fe6b0751" />
然后点击这个<img width="1296" height="607" alt="image" src="https://github.com/user-attachments/assets/0e50933e-4835-48ee-b946-4c40bd95ba86" />
我用的12.8.1，应该这两都可以，选择一个下载<img width="667" height="595" alt="image" src="https://github.com/user-attachments/assets/90b1524f-14cb-47c8-836f-1d74a9d58882" />
三、查看版本
在内置的python里面（ComfyUi\python或者ComfyUI_windows_portable\python_embeded）地址栏输入cmd,然后回车
在里面输入python -m pip list | findstr torch回车<img width="838" height="137" alt="image" src="https://github.com/user-attachments/assets/06d49283-a188-49bc-b098-8d0e901be867" />
输入python -m pip list | findstr sage 回车<img width="831" height="44" alt="image" src="https://github.com/user-attachments/assets/63094b9f-49f9-41fb-a2d5-41b1fd1c711b" />
输入python -m pip list | findstr triton 回车<img width="852" height="44" alt="image" src="https://github.com/user-attachments/assets/f4e75254-c36f-41cc-b71e-a588192d88c3" />

如果有的话会显示版本，没有好像是不显示
四、卸载torch
因为里面的很可能和自己的版本不同
刚才那个cmd页面，输入python -m pip uninstall torch torchaudio torchvision
后面会出现y/n,输入y，如果三个都有，要输入3次y
最后都successfully

五、安装torch（版本2.7.1）
还是刚才那个cmd页面，输入python -m pip install torch==2.7.1 torchvision==0.22.1 torchaudio==2.7.1 --index-url https://download.pytorch.org/whl/cu128
安装成功torch2.7.1

六、安装sageattention-2.2.0
下载文档里面的sageattention-2.2.0+cu128torch2.7.1-cp313-cp313-win_amd64.whl          #用的最新的comfyui portable，里面的python是3.13.6的，cp313就是用的3.13版本，要完全对应
找到它的下载位置，然后右键，复制文件地址
<img width="631" height="410" alt="image" src="https://github.com/user-attachments/assets/b975ba66-2370-48ad-8160-ccd20856b2d6" />

还是刚才那个cmd页面，输入python -m pip install -U 复制的文件地址    #直接把刚刚复制的文件地址复制过来就行，完整就是python -m pip install -U ".\.\sageattention-2.2.0+cu128torch2.7.1-cp313-cp313-win_amd64.whl"之类的
回车，然后successfully

七、安装triton-3.2.0
下载文档里面的triton-3.2.0-cp313-cp313-win_amd64.whl 
找到它的下载位置，然后右键，复制文件地址    #和上面那个一样

cmd中，输入python -m pip install 复制的文件地址                      #也是和上面一样，注意没有那个-U

八、检查版本
按照步骤一里面的查看版本，重新输入这三个指令，看看输入的版本是不是和安装的版本一致


这样就安装成功了


