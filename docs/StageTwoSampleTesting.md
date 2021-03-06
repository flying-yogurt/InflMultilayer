## Sample Data

```
           alpha      beta         gamma
        +---------+-----------+-------------+
        |  1 1 0  |  1 1 0 0  |  0 0 0 0 0  |
 alpha  |  1 1 1  |  0 0 0 0  |  0 0 1 0 0  |
        |  0 1 1  |  0 0 0 1  |  0 0 0 0 0  |
        +---------+-----------+-------------+
        |  1 0 0  |  1 0 0 0  |  0 0 0 0 0  |
  beta  |  1 0 0  |  0 1 0 1  |  1 0 0 0 1  |
        |  0 0 0  |  0 0 1 1  |  0 0 0 1 0  |
        |  0 0 1  |  0 1 1 1  |  0 1 0 0 0  |
        +---------+-----------+-------------+
        |  0 0 0  |  0 1 0 0  |  1 1 0 0 0  |
        |  0 0 0  |  0 0 0 1  |  1 1 1 0 1  |
 gamma  |  0 1 0  |  0 0 0 0  |  0 1 1 1 0  |
        |  0 0 0  |  0 0 1 0  |  0 0 1 1 0  |
        |  0 0 0  |  0 1 0 0  |  0 1 0 0 1  |
        +---------+-----------+-------------+
```

**Generation Codes:**

```py
import numpy as np

net = np.zeros((3,3), dtype=object)
g = net.shape[0]

net[0][0] = np.eye(3)
net[0][0][0][1] = 1
net[0][0][1][0] = 1
net[0][0][1][2] = 1
net[0][0][2][1] = 1

net[1][1] = np.eye(4)
net[1][1][1][3] = 1
net[1][1][3][1] = 1
net[1][1][2][3] = 1
net[1][1][3][2] = 1

net[2][2] = np.eye(5)
net[2][2][0][1] = 1
net[2][2][1][0] = 1
net[2][2][1][2] = 1
net[2][2][2][1] = 1
net[2][2][1][4] = 1
net[2][2][4][1] = 1
net[2][2][2][3] = 1
net[2][2][3][2] = 1

net[0][1] = np.zeros((3, 4))
net[0][1][0][0] = 1
net[0][1][0][1] = 1
net[0][1][2][3] = 1

net[0][2] = np.zeros((3, 5))
net[0][2][1][2] = 1


net[1][2] = np.zeros((4, 5))
net[1][2][1][0] = 1
net[1][2][1][4] = 1
net[1][2][2][3] = 1
net[1][2][3][1] = 1

net[1][0] = net[0][1].T
net[2][0] = net[0][2].T
net[2][1] = net[1][2].T
```

**Results:**

```
array([array([1.61535507, 1.64982991, 1.40824829]),
       array([1.57111426, 2.18646933, 1.40824829, 2.35395406]),
       array([1.62658704, 2.42275895, 1.85517172, 1.61237244, 1.62658704])],
      dtype=object)
```

**Figure:**

![](img/Sample_Network_Graph.svg)