## Primer paquete ROS2 propio (publisher + subscriber)

Conceptos:
- Un paquete ROS2 Python se crea con `ros2 pkg create --build-type ament_python`
- La clase base de todo nodo es `rclpy.node.Node`
- `create_publisher(tipo, topic, queue)` registra un publisher
- `create_subscription(tipo, topic, callback, queue)` registra un subscriber
- `create_timer(segundos, callback)` ejecuta una función periódicamente
- `rclpy.spin(node)` mantiene el nodo vivo escuchando eventos
- Los entry points en `setup.py` son lo que conecta el nombre del ejecutable con la función `main()`

Comandos:
- `ros2 pkg create --build-type ament_python --node-name <nodo> <paquete>`
- `colcon build` (desde la raíz del workspace)
- `source install/setup.bash` (tras cada build)
- `ros2 run <paquete> <nodo>`

Estructura del workspace:

```
ros2-learning/
└── src/
    └── primer_paquete/
        ├── package.xml
        ├── setup.py
        ├── setup.cfg
        └── primer_paquete/
            ├── __init__.py
            ├── my_first_node.py
            └── my_subscriber.py
```

Problema resuelto:
- Discovery entre terminales WSL: `export ROS_LOCALHOST_ONLY=1` en `~/.bashrc`