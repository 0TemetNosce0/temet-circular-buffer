# temet-circular-buffer
circular buffer stl



# example

```
#include <QDebug>
#include "include/circular_buffer.hpp"

cb::circular_buffer<int> cb(3);
// Insert some elements into the buffer.
cb.push_back(1);
cb.push_back(2);
cb.push_back(3);

int a1 = cb[0]; // a == 1
int b = cb[1]; // b == 2
int c = cb[2]; // c == 3
qDebug()<<a1<<b<<c;//1 2 3

// The buffer is full now, pushing subsequent
// elements will overwrite the front-most elements.

cb.push_back(4); // Overwrite 1 with 4.
cb.push_back(5); // Overwrite 2 with 5.
qDebug()<<cb.size()<<cb[0]<<cb[1]<<cb[2];//3 3 4 5

// The buffer now contains 3, 4 and 5.
a1 = cb[0]; // a == 3
b = cb[1]; // b == 4
c = cb[2]; // c == 5
qDebug()<<a1<<b<<c;//3 4 5

// Elements can be popped from either the front or the back.
cb.pop_back(); // 5 is removed.
cb.pop_front(); // 3 is removed.
int d = cb[0]; // d == 4
qDebug()<<cb.size()<<cb[0];//1 4
```

