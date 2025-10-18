# Reinforcement Learning Assignment 2

---

## Custom CNN Feature Extractor Flowchart

The network processes an input observation (like a stacked image frame from an Atari game) and outputs a fixed-size
feature vector.

$$
\begin{array}{|c|}
\hline
\textbf{Input Observation} \\
\text{(Tensor with shape } (C, 84, 84) \text{ where } C \text{ is the number of stacked frames)} \\
\hline
\end{array}
$$
$$\downarrow$$
$$
\begin{array}{|c|}
\hline
\textbf{Convolutional Layer 1 (Conv2d)} \\
\text{Filters: 32} \\
\text{Kernel Size: 8} \\
\text{Stride: 4} \\
\text{Padding: 0} \\
\text{Output Channels: 32} \\
\hline
\end{array}
$$
$$\downarrow$$
$$
\begin{array}{|c|}
\hline
\textbf{Rectified Linear Unit (ReLU)} \\
\hline
\end{array}
$$
$$\downarrow$$
$$
\begin{array}{|c|}
\hline
\textbf{Convolutional Layer 2 (Conv2d)} \\
\text{Filters: 64} \\
\text{Kernel Size: 4} \\
\text{Stride: 2} \\
\text{Padding: 0} \\
\text{Output Channels: 64} \\
\hline
\end{array}
$$
$$\downarrow$$
$$
\begin{array}{|c|}
\hline
\textbf{Rectified Linear Unit (ReLU)} \\
\hline
\end{array}
$$
$$\downarrow$$
$$
\begin{array}{|c|}
\hline
\textbf{Convolutional Layer 3 (Conv2d)} \\
\text{Filters: 64} \\
\text{Kernel Size: 3} \\
\text{Stride: 1} \\
\text{Padding: 0} \\
\text{Output Channels: 64} \\
\hline
\end{array}
$$
$$\downarrow$$
$$
\begin{array}{|c|}
\hline
\textbf{Rectified Linear Unit (ReLU)} \\
\hline
\end{array}
$$
$$\downarrow$$
$$
\begin{array}{|c|}
\hline
\textbf{Flatten} \\
\text{Converts the } (64, H_{out}, W_{out}) \text{ tensor into a single vector of size } n\_flatten \\
\hline
\end{array}
$$
$$\downarrow$$
$$
\begin{array}{|c|}
\hline
\textbf{Linear Layer (Fully Connected)} \\
\text{Input Size: } n\_flatten \\
\text{Output Size: } \textbf{features\_dim (512)} \\
\hline
\end{array}
$$
$$\downarrow$$
$$
\begin{array}{|c|}
\hline
\textbf{Rectified Linear Unit (ReLU)} \\
\hline
\end{array}
$$
$$\downarrow$$
$$
\begin{array}{|c|}
\hline
\textbf{Output Feature Vector} \\
\text{(Tensor with shape } (features\_dim) \text{, e.g., } (512) \text{)} \\
\hline
\end{array}
$$