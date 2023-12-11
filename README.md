# 1. Đầu tiên cần  cài đặt conda

# 2. Bước tiếp theo ta sẽ cài cài MARLlib với các bước sau : 

- conda create -n marllib python=3.8
- conda activate marllib
- git clone https://github.com/Replicable-MARL/MARLlib.git
- cd MARLlib
- pip install --upgrade pip
- pip install -r requirements.txt

- cd marllib
- pip3 install --upgrade protobuf==3.20.0
- python patch/add_patch.py -y


# 3. Sau khi cài xong MARLlib ta sẽ cài Mamujoco :

- mkdir /home/YourUserName/.mujoco
- cd /home/YourUserName/.mujoco
- wget https://roboti.us/download/mujoco200_linux.zip
- unzip mujoco200_linux.zip
- Sua thu muc  mujoco200_linux -> mujoco200
- export LD_LIBRARY_PATH=/home/YourUserName/.mujoco/mujoco200/bin;
- pip install mujoco-py==2.0.2.8

- git clone https://github.com/schroederdewitt/multiagent_mujoco
- cd multiagent_mujoco
- mv multiagent_mujoco /home/YourPathTo/MARLlib

- sudo apt-get install libosmesa6-dev
- pip install patchelf-wrapper==1.2.0
- Vào thư mục .mujoco tạo file mjkey.txt điền mjkey vào.


# 4. Add folder MARLlib vao IDE ( VSCode,..)
- Tao file exampleAPI.py ở trong thư mục MARLlib :


```
from marllib import marl

# prepare the environment
env = marl.make_env(environment_name="mpe", map_name="simple_spread", force_coop=True)

# initialize algorithm and load hyperparameters
mappo = marl.algos.mappo(hyperparam_source="mpe")

# build agent model based on env + algorithms + user preference if checked available
model = marl.build_model(env, mappo, {"core_arch": "mlp", "encode_layer": "128-256"})
```
***
	
- pip install "cython<3"
- pip install -r requirement.txt voi file requirement.txt có nội dung như sau:

***
```
asttokens==2.4.1
async-timeout==4.0.3
attrs==23.1.0
certifi==2023.11.17
cffi==1.16.0
charset-normalizer==3.3.2
click==8.1.7
cloudpickle==3.0.0
colorama==0.4.6
contourpy==1.1.1
cycler==0.12.1
Cython==0.29.36
dm-tree==0.1.8
executing==2.0.1
fasteners==0.19
filelock==3.13.1
fonttools==4.45.1
glfw==2.6.3
grpcio==1.59.3
gym==0.20.0
icecream==2.1.3
idna==3.6
imageio==2.33.0
importlib-metadata==4.13.0
importlib-resources==6.1.1
Jinja2==3.1.2
jsonschema==4.20.0
jsonschema-specifications==2023.11.1
kiwisolver==1.4.5
lz4==4.3.2
MarkupSafe==2.1.3
matplotlib==3.7.4
msgpack==1.0.7
mujoco-py==2.0.2.8
networkx==3.1
numpy==1.20.3
opencv-python==3.4.18.65
packaging==23.2
pandas==2.0.3
patchelf-wrapper==1.2.0
PettingZoo==1.12.0
Pillow==10.1.0
pkgutil_resolve_name==1.3.10
protobuf==3.20.3
pycparser==2.21
pyglet==2.0.10
Pygments==2.17.2
pyparsing==3.1.1
python-dateutil==2.8.2
pytz==2023.3.post1
PyWavelets==1.4.1
PyYAML==6.0.1
ray==1.8.0
redis==5.0.1
referencing==0.31.0
requests==2.31.0
rpds-py==0.13.1
scikit-image==0.19.3
scipy==1.10.1
six==1.16.0
SuperSuit==3.2.0
tabulate==0.9.0
tensorboardX==2.6.2.2
tifffile==2023.7.10
torch==1.9.0
typing_extensions==4.8.0
tzdata==2023.3
urllib3==2.1.0
zipp==3.17.0
```

***

- conda install -c conda-forge gcc=12.1.0

# 5. Sau khi cài xong như trên sẽ hiển ở bảng và thấy ở mamujoco có trạng thái là Ready ta sẽ thành công và bắt đầu config với các tham số và thuật toán.

