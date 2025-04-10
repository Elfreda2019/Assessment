# Assessment
Audio Deepfake Detection

## Part 1: Research & Selection
### 2 Forgery Detection models that detects AI-generated human speech, has potential for real-time or near real-time detection and can analysis real conversations best in my opinion are:
1. AASIST: Audio anti-spoofing using integrated spectro-temporal graph attention networks
2. Spoofing attacker also benefits from self-supervised pretrained model
3. End-to-End Dual-Branch Network Towards Synthetic Speech Detection


### 3  Brief Summary: 
#### 1. AASIST: Audio anti-spoofing using integrated spectro-temporal graph attention networks
##### Key technical innovation
1. It integrates spectro-temporal graph attention networks to capture both the temporal and spectral properties of speech, allowing the model to focus on critical regions in the 
   audio signal.
2. The RawNet2 network and the integration of attention mechanisms (via HS-GAL) further enhance the model's ability to process raw audio efficiently.

##### Reported performance metrics:
1. EER: LA: 0.83% (Ranked 2nd)
2. t-DCF: LA: 0.028 (Ranked 1st)

##### Why It’s Promising for our specific needs:
1. The attention mechanisms (HS-GAL) allow it to focus on relevant speech features, improving accuracy in detecting AI-generated voices.
2. The low EER and t-DCF indicate strong performance in identifying spoofed audio, making it well-suited for real-time conversation analysis.
3. RawNet2 ensures efficient processing, which is crucial for low-latency applications.

##### Potential limitations or challenges:
1. The integration of complex attention mechanisms could introduce additional computational overhead, potentially impacting real-time performance in highly demanding environments.
2. Fine-tuning for diverse real-world audio conditions may be required to achieve optimal results.

#### 2. Spoofing attacker also benefits from self-supervised pretrained model
##### Key technical innovation
1. It utilizes self-supervised learning (HuBERT, WavLM) for feature extraction, allowing the model to adapt to diverse speech data without the need for large labeled datasets.
2. Thd residual block and Conv-TasNet architecture designed for raw waveform processing, optimizes real-time performance.

##### Reported performance metrics:
1. EER: 0.44% (Ranked 1st)
2. t-DCF: No reported value, but likely highly efficient due to its low EER.

##### Why It’s Promising for our specific needs:
1. The self-supervised learning enables the model to generalize well across various speech data, including synthetic voices.
2. It has real-time efficiency due to the raw waveform-based architecture.
3. It can handle the complex and noisy environment of real conversations effectively.

##### Potential limitations or challenges:
1. Lack of the t-DCF makes it harder to fully evaluate its performance in real-world settings in terms of false positives and negatives.
2. It might require additional fine-tuning for specific conversational contexts, though self-supervised nature helps mitigate this challenge.

#### 3. End-to-End Dual-Branch Network Towards Synthetic Speech Detection
##### Key technical innovation:
1. Dual-branch network architecture allows the model to separately process spectral and temporal features, enhancing its ability to distinguish between real and fake speech.
2. LFCC and CQT features ensure both frequency and temporal aspects of speech are captured.

##### Reported performance metrics:
1. EER: 0.80% (Ranked 1st)
2. t-DCF: 0.021 (Ranked 1st)

##### Why It’s Promising for our specific needs:
1. The low EER and t-DCF values show that this model can effectively differentiate between synthetic and real speech with minimal error.
2. The dual-branch structure and rich feature extraction make it adaptable for detecting various speech manipulations in real conversations.
3. It has a real-time detection potential due to efficient processing pipelines.

##### Potential limitations or challenges:
1. Might require significant computational resources for real-time deployment, especially in high-volume environments.
2. The dual-branch nature may increase complexity, which could impact scalability.


## Part 2: Implementation
For implementation, I will select the End-to-End Dual-Branch Network Towards Synthetic Speech Detection model. This choice is motivated by its excellent reported performance metrics (EER: 0.80%, t-DCF: 0.021) and its ability to effectively differentiate between synthetic and real speech. The dual-branch architecture, which processes spectral and temporal features separately, provides strong performance in detecting AI-generated human speech while being adaptable for real-time applications.

Implementation Plan for the Dual-Branch Network
Data Preprocessing:






