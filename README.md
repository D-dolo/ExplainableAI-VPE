# 🧠 Zero-Shot Digit Recognition with Interpretable Generative Models

This master thesis project explores a novel approach to zero-shot learning in handwritten digit recognition using a Variational Prototyping Encoder (VPE). By combining prototypical representations with a concept bottleneck layer, the model learns to recognize both seen and unseen digits through interpretable visual concepts.

## 🔬 Key Features
- Zero-Shot Generalization: Classifies digits never seen during training by relying on visual similarity and concept encoding.

- Concept Bottleneck Layer: Predicts human-interpretable visual concepts like:

    - Circularity

    - Pixel density

    - Aspect ratio

    - Orientation

    - Loopiness

- Epsilon-Greedy Loss Function:
A novel loss mechanism is introduced, combining multiple loss components to enhance training. This approach balances exploration and exploitation, allowing the model to escape local optima and discover better solutions.

- Strong Performance: Achieves competitive reconstruction and classification accuracy on MNIST, even for unseen digit classes.

- Interpretability Built-In: Uses t-SNE, Integrated Gradients, and Concept Activation Vectors (CAVs) to visualize and explain the model's decisions.

- Human-Aligned Representations: Latent space clusters reflect meaningful visual groupings, mirroring how humans might perceive similarity.

## 🚀 Why It Matters

This work pushes the boundaries of explainable AI (XAI) and few-shot/zero-shot learning, showing how generative models can be both powerful and interpretable. It's a step toward models that don't just perform well, but also make sense to humans.

# 🛠️ Getting Started

Follow these steps to set up and run the project locally:
1) Clone the repository
2) Create a virtual environment (optional but recommended)
3) Install dependencies: [`requirements.txt`](requirements.txt/re)<pre>pip install -r requirements.txt</pre>
4) Run the notebook: [`VPE_Final.ipynb`](./VPE_Final.ipynb)

# 🧽 Image Standardization with [`prototype_stdize.ipynb`](./prototype_stdize.ipynb)

To ensure consistency in digit prototypes used for training and concept extraction, this notebook standardizes all digit images into a uniform format.

## 📐 What it does:
- Converts images to grayscale.

- Automatically detects and crops the digit from each image.

- Resizes it proportionally to fit a 64×64 square.

- Centers the digit on a white background.

- Saves the standardized images for consistent downstream processing.

## 🔧 Example usage (in Python):
<pre>standardize_image_smart("prototypes/5.png", "prototypes/standardized_prototypes/5.png")
</pre>
Or run it on all `.png` files in the `prototypes/` folder automatically by executing the notebook [`prototype_stdize.ipynb`](./prototype_stdize.ipynb)

This step is especially useful if you're using hand-designed or externally sourced prototype digits that vary in size or alignment.