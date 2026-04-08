# Activation Functions

---

## Sigmoid Activation Function
**Description:** A mathematical function with a characteristic "S"-shaped curve that maps any real-valued number into a probability range strictly between 0 and 1.

**Content:** Sigmoid takes any input, no matter how large or small, and squashes it into a tight range.

**Formula:**
$$f(x) = \frac{1}{1 + e^{-x}}$$

**Example:** In a binary classification model designed to detect network intrusions, the final output needs to be a clear probability. If the raw neural network calculation results in a score of 15.4, Sigmoid squashes that into 0.999, meaning there is a 99.9% probability the packet is malicious.

**When to use:** Use it exclusively in the output layer of a binary classification model. Never use it in hidden layers because of the "vanishing gradient problem"—when inputs are very high or very low, the curve becomes perfectly flat, the gradient drops to zero, and the network completely stops learning.

---

## Tanh (Hyperbolic Tangent)
**Description:** A scaled, zero-centered version of the sigmoid function that maps inputs to a range between -1 and 1.

**Content:** Tanh looks exactly like Sigmoid, but it crosses through the origin (0,0). Because the outputs are zero-centered, the math during optimization (gradient descent) flows much smoother and converges faster than Sigmoid.

**Formula:**
$$f(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}}$$

**Example:** If you are coding the AI for an NPC in a game, and the network needs to output a steering direction. An output of -1 means steer hard left, 1 means steer hard right, and 0 means walk straight ahead. Tanh perfectly represents this directional variance.

**When to use:** Use it in the hidden layers of Recurrent Neural Networks (RNNs) or when you specifically need the model's internal representations to have both negative and positive signs. It is almost always strictly better than Sigmoid for hidden layers, though it still suffers from the vanishing gradient problem at extreme values.

---

## ReLU (Rectified Linear Unit)
**Description:** A highly efficient, piecewise linear function that outputs the input directly if it is positive, and outputs absolute zero if it is negative.

**Content:** ReLU is incredibly simple but revolutionized deep learning. It does not squash the positive values, meaning the gradient never vanishes for positive numbers. This allows models with dozens or hundreds of layers to train incredibly fast.

**Formula:**
$$f(x) = \max(0, x)$$

**Example:** Imagine a neural network scanning a file for a specific malicious signature. ReLU acts as an instantaneous gatekeeper. If the feature calculation is negative (signature not found), ReLU outputs a hard 0, immediately shutting off that neuron and saving computational power. If it's positive, it passes the exact magnitude of that detection forward.

**When to use:** ReLU is the absolute gold standard, default activation function for the hidden layers of almost all modern neural networks (like CNNs and standard Multilayer Perceptrons).

---

## Review Note: Activation Functions

### Core Learning
*   **Activation functions** decide whether a neuron should "fire" or not.
*   **Sigmoid:** Output layer (Binary probability: 0 to 1).
*   **Tanh:** RNN hidden layers (Zero-centered: -1 to 1).
*   **ReLU:** CNN/Deep hidden layers (Fast, no maximum limit: 0 to infinity).

### Points of Confusion to Review
*   I need to remember the difference between **Vanishing Gradient** (Sigmoid/Tanh getting too flat at the ends) and the **Dying ReLU problem** (when a ReLU neuron gets pushed into the negative range and permanently outputs 0, effectively "dying" and never updating again). 
*   I'll want to mention "Leaky ReLU" as the fix for Dying ReLU in an interview.