# `Scribble to Script`
# **ABSTRACT**
Handwritten text recognition remains a challenging task due to variations in writing styles, noise, and 
segmentation complexities. This report explores the application of Long Short-Term Memory (LSTM) networks 
for handwritten detection. We propose a system that leverages the sequential learning capabilities of LSTMs to 
effectively capture the temporal dependencies within handwritten characters and words.
The report details the system architecture, encompassing pre-processing techniques for noise reduction 
and image preparation. We outline the LSTM network design, including the choice of hyperparameters and the 
training process. The Connectionist Temporal Classification (CTC) loss function is employed to handle the 
inherent variability of handwritten text lengths.
The report presents the evaluation methodology, including the chosen handwritten text dataset and performance 
metrics. We discuss the achieved accuracy of the system in detecting handwritten text and compare it to potential 
baseline approaches.
Finally, the report concludes by summarizing the findings and potential areas for future exploration. We discuss 
the limitations of the current system and propose avenues for improvement, such as incorporating additional preprocessing steps or investigating advanced LSTM architectures

# **1. INTRODUCTION**
Handwritten text recognition, the ability for computers to decipher our scribbles, remains a complex task. 
Variations in writing styles, noisy images, and difficulties in separating characters all pose challenges. This report 
explores a promising approach: leveraging Long Short-Term Memory (LSTM) networks to tackle handwritten 
text detection. LSTMs, a type of artificial intelligence, excel at understanding sequential data. In our case, the 
sequence is the order of strokes that form a character, and ultimately, a word. By employing LSTMs, we aim to 
develop a system that can effectively capture these sequential relationships within handwritten text.
This report delves into the details of this system, including the methods used to prepare the images for 
analysis and the design of the LSTM network itself. We'll explore the training process and a specific technique, 
called Connectionist Temporal Classification, that helps the network handle the variable lengths of handwritten 
text. Furthermore, we'll establish how the system's performance is measured and compared to other approaches. 
Finally, the report concludes by summarizing the findings and outlining potential avenues for further 
development to enhance the accuracy and robustness of this handwritten text recognition system.
# 1.1 Existing system:
While this report focuses on LSTMs for handwritten text recognition, it's valuable to acknowledge 
existing systems that have tackled this challenge. Here's a brief overview:
• Traditional Techniques: These methods often rely on rule-based approaches for character extraction 
and recognition. They involve feature extraction from individual characters followed by matching them 
to pre-defined templates. While effective for some scenarios, they struggle with significant variations in 
handwriting styles.
• Optical Character Recognition (OCR) engines: Primarily designed for printed text, OCR engines 
can sometimes handle "printed" handwriting (capital letters) with decent accuracy. However, they often 
falter with cursive or more stylistic handwriting.
• Deep Learning Approaches: In recent years, deep learning, particularly Convolutional Neural 
Networks (CNNs), have shown promising results in handwritten text recognition. CNNs excel at 
extracting relevant features from images, making them suitable for analysing handwritten characters.
# 1.2 Proposed systems:
This report proposes a system for handwritten text recognition that utilizes the strengths of Long ShortTerm Memory (LSTM) networks. LSTMs are a type of recurrent neural network specifically designed to handle 
sequential data, making them ideal for capturing the order and relationships between strokes that form characters 
and words in handwritten text.
The system can be broken down into three key stages:
1. Pre-processing:
• The initial stage involves preparing the input image for the LSTM network. This may include techniques 
like noise reduction, binarization (converting the image to black and white), and normalization (ensuring 
images have consistent sizes).
• Additionally, depending on the complexity of the handwriting, segmentation techniques might be 
employed to separate individual characters or words before feeding them into the network.
2. LSTM Network Design:
• The core of the system is the LSTM network. The specific architecture will be detailed later in the report, 
including the number of LSTM layers, hidden units, and activation functions.
• A crucial aspect is selecting appropriate hyperparameters, which are essentially the tuning knobs of the 
network that influence its learning behavior.
• Training the network involves feeding it a large dataset of pre-processed handwritten text images paired 
with their corresponding text labels. During training, the network learns to identify patterns and 
relationships within the sequential data of handwritten strokes.
3. Connectionist Temporal Classification (CTC):
• A key challenge in handwritten text recognition is the varying lengths of words and sentences. Traditional 
loss functions might struggle with this variability.
• This is where Connectionist Temporal Classification (CTC) comes in. CTC is a specialized technique 
that allows the network to handle sequences of different lengths, making it well-suited for handwritten 
text with variable word counts.
