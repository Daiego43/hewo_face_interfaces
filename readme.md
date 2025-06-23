# 🧩 hewo_face_interfaces

This package defines the **ROS 2 message interfaces** used by the HeWo face module (`hewo-face`) and its ROS wrapper (`hewo_face_pkg`).  
These messages are used to express emotions, face positioning, and fine-grained emotional adjustments for the HeWo robot.

---

## 📦 Message Definitions

### 📌 `Emotion.msg`

Used to represent a full emotional state by providing multiple emotion keys and their corresponding values.

```plaintext
string[] keys
int32[] values
````

* `keys`: List of emotion parameter IDs.
* `values`: Corresponding values between `0` and `100` for each emotion component

---

### 🎯 `AdjustEmotionPoint.msg`

Used to adjust a single emotional parameter dynamically.

```plaintext
string param
int32 value
```

* `param`: The name of the emotion key to adjust
* `value`: The new value to apply to that parameter (clamped to 0–100 inside the node logic)

---

### 🕹️ `AdjustPosition.msg`

Used to adjust the face position by delta offsets.

```plaintext
int32 dx
int32 dy
```

* `dx`: Horizontal position offset (pixels)
* `dy`: Vertical position offset (pixels)

---

## 🔧 Usage

These messages are published and subscribed to by the [`hewo_face_pkg`](https://github.com/ThinThought/hewo_face_pkg) nodes.
They allow external components (like a web interface, controller, or other ROS nodes) to interact with the expressive face of HeWo in real time.

---

## 🧼 Author

Developed by [Diego Delgado Chaves](mailto:diedelcha@gmail.com)
License: MIT


