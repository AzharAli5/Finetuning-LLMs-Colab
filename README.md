<section id="project-header">
    <h1>📄 Finetuning Llama-3-1B on Resume Dataset</h1>
    <div class="badges">
        <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License">
        <img src="https://img.shields.io/badge/python-3.10+-blue.svg" alt="Python Version">
    </div>
</section>

<section id="dataset">
    <h2>📁 Dataset</h2>
    <p>
        Using the <a href="https://huggingface.co/datasets/AzharAli05/Resume-Screening-Dataset" target="_blank">
        Resume Screening Dataset</a> from Hugging Face
    </p>
    <ul>
        <li><strong>Columns:</strong> Role, Resume, Decision, Reason_for_decision, Job_Description</li>
        <li><strong>Entries:</strong> 500+ annotated resumes</li>
    </ul>
</section>

<section id="features">
    <h2>🚀 Features</h2>
    <ul>
        <li>4-bit QLoRA fine-tuning</li>
        <li>VRAM &lt; 8GB requirements</li>
        <li>Unsloth-optimized training</li>
    </ul>
</section>

<section id="installation">
    <h2>⚙️ Installation</h2>
    <pre><code>git clone https://github.com/AzharAli5/resume-screener-llama3.git
cd resume-screener-llama3
pip install -r requirements.txt</code></pre>
</section>

<section id="training">
    <h2>🧠 Training Parameters</h2>
    <table>
        <thead>
            <tr>
                <th>Parameter</th>
                <th>Value</th>
            </tr>
        </thead>
        <tbody>
            <tr><td>Batch size</td><td>4</td></tr>
            <tr><td>Learning rate</td><td>2e-5</td></tr>
            <tr><td>Epochs</td><td>3</td></tr>
        </tbody>
    </table>
</section>

<section id="usage">
    <h2>💻 Usage Example</h2>
    <pre><code class="language-python">from unsloth import FastLanguageModel

model, tokenizer = FastLanguageModel.from_pretrained(
    model_name = "./model",
    max_seq_length = 2048,
)

inputs = tokenizer.apply_chat_template([...], return_tensors="pt")
outputs = model.generate(inputs, max_new_tokens=256)</code></pre>
</section>

<section id="structure">
    <h2>📂 Repository Structure</h2>
    <pre>
.
├── data/
├── outputs/
├── train.py
└── requirements.txt</pre>
</section>
</section>
