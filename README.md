# ✈️ Plane Model Type Identifier

> A deep learning image classifier that identifies 100 specific commercial aircraft variants from photos — built as a final project for ID Tech.
>
> ---
>
> ## 🧠 Overview
>
> This project fine-tunes a **ResNet-50** convolutional neural network on the **FGVC-Aircraft** dataset to classify 100 specific aircraft model variants (e.g., Boeing 737-800, Airbus A320, 707-320). The model is trained entirely in a **Google Colab** notebook using **PyTorch** and runs on a GPU (CUDA).
>
> The full pipeline covers: dataset download & preprocessing, transfer learning with ResNet-50, training with cosine annealing LR scheduling, validation accuracy tracking, and model export.
>
> ---
>
> ## 🚀 Features
>
> - Classifies **100 aircraft model variants** from the FGVC-Aircraft benchmark dataset
> - - **Transfer learning** with a pretrained ResNet-50 backbone (ImageNet weights), fine-tuned end-to-end
>   - - **Data augmentation**: random resized crop, horizontal flip, color jitter, ImageNet normalization
>     - - **AdamW optimizer** with cosine annealing learning rate scheduler
>       - - **Label smoothing** (0.1) in the cross-entropy loss for better generalization
>         - - Training & validation accuracy/loss curves plotted and saved as `training_curves.png`
>           - - Model weights saved as `resnet50_aircraft_classifier.pth`
>             - - Runs on GPU via Google Colab (T4 tested)
>              
>               - ---
>
> ## 📁 Project Structure
>
> ```
> Plane/
> ├── Copy_of_jupyter.ipynb   # Main Colab notebook (training pipeline)
> ├── resnet50_aircraft_classifier.pth  # Saved model weights (after training)
> ├── training_curves.png     # Loss & accuracy plots (generated after training)
> ├── data/                   # FGVC-Aircraft dataset (auto-downloaded)
> │   └── fgvc-aircraft-2013b/
> └── README.md
> ```
>
> ---
>
> ## 🛠️ Tech Stack
>
> | Tool | Purpose |
> |------|---------|
> | Python 3.x | Core language |
> | PyTorch 2.x | Model building, training & inference |
> | Torchvision | FGVC-Aircraft dataset + ResNet-50 pretrained weights |
> | NumPy | Numerical operations |
> | Matplotlib | Training curve visualizations |
> | Google Colab (T4 GPU) | Training environment |
>
> ---
>
> ## ⚙️ Setup & Usage
>
> ### 1. Open the Notebook in Google Colab
>
> Open `Copy_of_jupyter.ipynb` in [Google Colab](https://colab.research.google.com/) and make sure a GPU runtime is selected (**Runtime → Change runtime type → T4 GPU**).
>
> ### 2. Run All Cells
>
> The notebook will automatically:
>
> 1. Install/import all required libraries
> 2. 2. Download the FGVC-Aircraft dataset (~2.75 GB) via `torchvision`
>    3. 3. Build a ResNet-50 model with a 100-class output head
>       4. 4. Train for 10 epochs and print per-epoch metrics
>          5. 5. Plot and save training curves to `training_curves.png`
>             6. 6. Save model weights to `resnet50_aircraft_classifier.pth`
>               
>                7. ---
>               
>                8. ## 📊 Model Performance (10 Epochs)
>               
>                9. | Epoch | Train Loss | Train Acc | Val Loss | Val Acc |
> |-------|-----------|-----------|---------|---------|
> | 1     | 4.4570    | 5.37%     | 3.8915  | 16.56%  |
> | 2     | 3.2646    | 32.36%    | 2.8406  | 33.42%  |
> | 3     | 2.2899    | 56.90%    | 2.2640  | 49.89%  |
> | 4     | 1.8123    | 71.00%    | 2.0360  | 57.79%  |
> | 5     | 1.5274    | 80.74%    | 1.9352  | 61.66%  |
> | 6     | 1.3360    | 87.79%    | 1.8266  | 64.69%  |
> | 7     | 1.2279    | 91.48%    | 1.7514  | 68.05%  |
>
> > Training was still in progress at epoch 7 at time of writing. Best validation accuracy reached: **68.05%**.
> >
> > ---
> >
> > ## 🛩️ Dataset: FGVC-Aircraft
> >
> > The [FGVC-Aircraft](https://www.robots.ox.ac.uk/~vgg/data/fgvc-aircraft/) benchmark contains images of aircraft with annotations at multiple levels of granularity. This project uses the **variant** level (100 classes — the most fine-grained), e.g.:
> >
> > - 707-320, 727-200, 737-200 through 737-900
> > - - 747-100 through 747-400
> >   - - A318, A319, A320, A321, A330, A340, A380
> >     - - Many more regional jets, turboprops, and general aviation types
> >      
> >       - **Dataset split used:**
> >       - - Train: 3,334 images
> >         - - Validation: 3,333 images
> >          
> >           - ---
> >
> > ## 📌 Future Improvements
> >
> > - Continue training beyond 10 epochs for higher validation accuracy
> > - - Experiment with stronger backbones (EfficientNet-B4, ViT) for improved accuracy
> >   - - Add top-5 accuracy metric
> >     - - Build a simple web interface (Flask or Streamlit) for drag-and-drop predictions
> >       - - Export to ONNX for portable inference
> >        
> >         - ---
> >
> > ## 👤 Author
> >
> > **Daniel** — [daniel061210](https://github.com/daniel061210)
> >
> > ID Tech Final Project — 2026
> >
> > ---
> >
> > ## 📄 License
> >
> > This project is open source and available under the [MIT License](LICENSE).
