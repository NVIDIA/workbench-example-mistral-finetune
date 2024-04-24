# NVIDIA AI Workbench: Introduction
This is an [NVIDIA AI Workbench](https://www.nvidia.com/en-us/deep-learning-ai/solutions/data-science/workbench/) example Project that demonstrates how to fine-tune a Mistral 7B large language model on a custom code instructions dataset using the QLoRA PEFT method. Users who have [installed AI Workbench](https://www.nvidia.com/en-us/deep-learning-ai/solutions/data-science/workbench/) can get up and running with this project in minutes. Please note the project requirements: 

* Operating System: Ubuntu 22.04, Windows (WSL2), MacOS 12+
* CPU requirements: None, (tested with Intel&reg; Xeon&reg; Platinum 8380 CPU @ 2.30GHz)
* GPU requirements: See Below

### Sizing Guide

| GPU VRAM | Example Hardware | Compatible? | Additional Notes |
| -------- | ------- | ------- | ------- |
| 24 GB | RTX 3090/4090, RTX A5000/5500, A10/30 | Y | slow on 8-bit and full precision |
| 32 GB | RTX 5000 Ada,  | Y | N/A |
| 40 GB | A100-40GB | Y | N/A |
| 48 GB | RTX 6000 Ada, L40/L40S, A40 | Y | N/A |
| 80 GB | A100-80GB | Y | N/A |
| >80 GB | 8x A100-80GB | Y | N/A |

## Project Description
Mistral 7B is a recent open-source language model developed by MistralAI that consistently delivers state-of-the-art results across a variety of natural language understanding and generation benchmarks. While this model serves as a strong baseline for multiple downstream tasks, it can lack in domain-specific knowledge or proprietary or otherwise sensitive information. Fine-tuning is often used as a means to update a model for a specific task or tasks to better respond to domain-specific prompts. This notebook walks through downloading the Mistral 7B model from Hugging Face, preparing a custom dataset on coding-related tasks and instructions, and using Quantized Low Rank Adaptation (QLoRA) to fine-tune the base model against the dataset. While we focus on a coding-specific task in this example, this methodology can be applied seamlessly to other tasks and data as well.

Have questions? Please direct any issues, fixes, suggestions, and discussion on this project to the DevZone Members Only Forum thread [here](https://forums.developer.nvidia.com/t/support-workbench-example-project-mistral-finetune/278376/1). 

# Quickstart

### Prerequisites
As of April 2024, this model is gated by Hugging Face. Please complete the following to ensure access to the model. 

1. Create/Login to your Hugging Face Account and generate an Access Token [here](https://huggingface.co/settings/tokens).

2. Navigate to the base model card [here](https://huggingface.co/mistralai/Mistral-7B-v0.1) and select "Agree and access repository". You should then see a "You have been granted access to this model" message appear on the model card. 

### On Desktop
If you do not NVIDIA AI Workbench installed, first follow the installation instructions for AI Workbench [here](https://www.nvidia.com/en-us/deep-learning-ai/solutions/data-science/workbench/). Then, 

1. Fork this Project to your own GitHub namespace and copy the link

   ```
   https://github.com/[your_namespace]/<project_name>
   ```
   
2. Open NVIDIA AI Workbench. Select a location to work in. 
   
3. Clone this Project onto your desired machine by selecting **Clone Project** and providing the GitHub link.
   
4. Wait for the project to build. You can expand the bottom **Building** indicator to view real-time build logs. 

5. When the build completes, set the following configurations.

   * `Environment` > `Secrets` > `Configure`. Specify the Hugging Face Hub Access Token you created and configured in the Prerequisites section.

   * `Environment` > `Mounts` > `Configure`. Specify the file path of the mount, eg. where the fine-tuned Mistral model will live on your **host** machine.
   
      eg. if you would like your model directory to reside on your home path, enter ```/home/[user]```

6. On the top right of the window, select **Jupyterlab**. 

7. Navigate to the code directory of the project. Then, open the fine-tuning notebook and get started. Happy coding!

### On CLI
Get started in the CLI by: 

1. Forking this Project to your own GitHub namespace and copying the link

   ```
   https://github.com/[your_namespace]/<project_name>
   ```
   
2. Opening a shell and activating the Context you want to clone into by

   ```
   $ nvwb list contexts
   
   $ nvwb activate <desired_context>
   ```
   
3. Cloning this Project onto your desired machine by running

   ```
   $ nvwb clone project <your_project_link>
   ```
   
4. Opening the Project by

   ```
   $ nvwb list projects
   
   $ nvwb open <project_name>
   ```
   
5. Starting JupyterLab by

   ```
   $ nvwb start jupyterlab
   ```

   * You may need to specify your Hugging Face Hub Access Token you created and configured in the Prerequisites section as a project secret.
   
   * You may need to specify the file path of the mount, eg. where the fine-tuned Mistral model will live on your **host** machine, eg. if you would like your model directory to reside on the home path of the host system, enter ```/home/[user]```

6. Navigate to the `code` directory of the project. Then, open your Mistral fine-tuning notebook of choice and get started. Happy coding!

---
**Tip:** Use ```nvwb help``` to see a full list of NVIDIA AI Workbench commands. 

---

## Tested On
This notebook has been tested with an NVIDIA RTX A6000 GPU and the following version of NVIDIA AI Workbench: ```nvwb 0.21.3 (internal; linux; amd64; go1.21.3; Tue Mar  5 03:55:43 UTC 2024)```

# License
This NVIDIA AI Workbench example project is under the [Apache 2.0 License](https://github.com/NVIDIA/workbench-example-mistral-finetune/blob/main/LICENSE.txt)

This project will download and install additional third-party open source software projects. Review the license terms of these open source projects before use. Third party components used as part of this project are subject to their separate legal notices or terms that accompany the components. You are responsible for confirming compliance with third-party component license terms and requirements. 
