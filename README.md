# StudioChat
Working, not finished. Powershell-Core Multi-Window Chatbot with LM Studio hosted model(s). 

### DEVELOPMENT NOTES..
Early stages, it is limited. After upgrades below, there will be a review. The plan from here is...
1.  programmatically snap windows to specific corners of the screen in Windows 10 using PowerShell Core.
2. format of window should include borders, and re-draw, displaying, "current" and "recent" and "so-far", events, these will have to be consolidated by the model additionally.
3. Prompt Sent to AI with insertion of consolidated interactions in, current and recent and so-far, sections.  
4. 2 Windows need re-formatting to 2 halves of a widescreen.
5. Some kind of model for Image Generation, then use playground mode on LM Studio.
6. Requires to be created Window 3 for Graphics output, this can be based on description of "So-Far".

### RESEARCH:
- Noteworthy is a Llama 3 Instruct-Chat Merge in 20B Paramneters, weighing around 20GB, quite acceptable for multi-line output and input, but possibly filtered. This is being investigated for use with development version of StudioChat - https://huggingface.co/AtakanTekparmak/llama-3-20b-instruct-Q8_0-GGUF/tree/main . At some point will be using New Qwen-2 model, beating Llam 3 and producing GPT4 quality output - https://www.youtube.com/watch?v=4vrK_LvMHNM , https://huggingface.co/models?sort=downloads&search=Qwen2+57b+gguf .
- Powershell 7.5 Beta, PowerShell Core beta updates can significantly enhance a local model chatbot by improving data handling with ConvertTo-Json serialization of BigInteger, providing actionable error suggestions, and adding a progress bar to Remove-Item. Enhanced path handling, early resolver registration, and improved error formatting boost stability and usability. Process management fixes allow better credential handling without admin privileges and easier process monitoring, while improved stream redirection enhances integration with native applications. These updates collectively enhance robustness, efficiency, and user experience for local model chatbots.


## FEATURES:
- 2 Windows, Engine and Chat, taking up 1/4 of a widescreen display, 1/2 total.
- Multi-line input via Shift+Enter, no ability to return to earlier lines, entered with Enter at end. 


...

TBA
