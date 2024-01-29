# NVIDIA AI Workbench: Introduction
This is an [NVIDIA AI Workbench](https://developer.nvidia.com/blog/develop-and-deploy-scalable-generative-ai-models-seamlessly-with-nvidia-ai-workbench/) example Project that demonstrates how to fine-tune a Mistral 7B large language model on a custom code instructions dataset using the QLoRA PEFT method. Users in the [AI Workbench Beta Program](https://developer.nvidia.com/ai-workbench-beta) can get up and running with this Project in minutes. 

Have questions? Please direct any issues, fixes, suggestions, and discussion on this project to the DevZone Members Only Forum thread [here](https://forums.developer.nvidia.com/t/support-workbench-example-project-mistral-finetune/278376/1). 

## Project Description
Mistral 7B is a recent open-source language model developed by MistralAI that consistently delivers state-of-the-art results across a variety of natural language understanding and generation benchmarks. While this model serves as a strong baseline for multiple downstream tasks, it can lack in domain-specific knowledge or proprietary or otherwise sensitive information. Fine-tuning is often used as a means to update a model for a specific task or tasks to better respond to domain-specific prompts. This notebook walks through downloading the Mistral 7B model from Hugging Face, preparing a custom dataset on coding-related tasks and instructions, and using Quantized Low Rank Adaptation (QLoRA) to fine-tune the base model against the dataset. While we focus on a coding-specific task in this example, this methodology can be applied seamlessly to other tasks and data as well.

## System Requirements:
* Operating System: Linux, Windows WSL, or Mac; tested on Ubuntu 20.04
* CPU requirements: None, tested with Intel&reg; Xeon&reg; Platinum 8380 CPU @ 2.30GHz
* GPU requirements: Any NVIDIA training GPU, tested with NVIDIA A100-80GB
* NVIDIA driver requirements: Latest driver version
* Storage requirements: 40GB

# Quickstart
If you have NVIDIA AI Workbench already installed, you can open this Project in AI Workbench on your choice of machine by:

### On Desktop
Fork this Project to your own Github namespace and copy the clone link. Open the Desktop app and select your location of choice. Select "Clone Project" and enter the clone link. Wait for the build to complete. 

Once the build completes, select "Open Jupyterlab" on the top right corner to start the application in a new window. Navigate to the `code` directory of the project. Then, open your Mistral fine-tuning notebook of choice and get started. Happy coding!

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

6. Navigate to the `code` directory of the project. Then, open your Mistral fine-tuning notebook of choice and get started. Happy coding!

---
**Tip:** Use ```nvwb help``` to see a full list of NVIDIA AI Workbench commands. 

---

## Tested On
This notebook has been tested with an NVIDIA A100-80gb GPU and the following version of NVIDIA AI Workbench: ```nvwb 0.13.2 (internal; linux; amd64; go1.21.3; Sat Dec 23 17:47:46 UTC 2023)```

# License
This NVIDIA AI Workbench example project is under the [Apache 2.0 License](https://github.com/NVIDIA/workbench-example-mistral-finetune/blob/main/LICENSE.txt)

This project will download and install additional third-party open source software projects. Review the license terms of these open source projects before use. Third party components used as part of this project are subject to their separate legal notices or terms that accompany the components. You are responsible for confirming compliance with third-party component license terms and requirements. 
