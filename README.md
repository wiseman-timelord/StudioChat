# Studio-Chat
Status: Working. Release (old) version is working for no webui; README.md shown is partly/mostly for upcoming version. 

### DEVELOPMENT NOTES..
- DeepSeek v2.5 is able to take the full load of the scripts, and produce descriptions such as shown below.
2. I decided to...
```
A roleplaying AI software that integrates a Gradio interface for the main chat interaction and a PowerShell engine window for handling text menus and model processing. The Gradio interface features a 2x2 grid layout with a row for user input, while the engine window switches between "engine mode" for processing models and "menus mode" for displaying text menus. The engine window also displays a waiting message enabling the user to return to the menu, when no processing of responses/recent interactions/scenario/history cycle is going on. The program uses a TCP server to facilitate communication between the Gradio interface and the engine window, ensuring seamless interaction and log message handling.
```

### DESCRIPTION:
- Powershell-Core Multi-Window Chatbot with LM Studio hosted model(s). A roleplaying AI software that leverages LM Studio for generating responses in a roleplaying scenario. The software is designed to be user-friendly, with a Gradio web interface for user interaction and a Python text window for engine operations. The system includes functions for configuring the window, managing configurations, generating and filtering responses, and handling TCP communication. The software aims to provide an immersive roleplaying experience while remaining manageable in terms of size and complexity for AI programming improvements.

## FEATURES:
- **Gradio Interface**: The Roleplaying WebUi with Gradio in a self-terminating sub-process.
- **LM Studio Interaction**: Generates and filters responses using LM Studio.
- **Chat and Consolidation Handling**: Manages chat messages and consolidates responses.
- **Configuration Management**: Loads and applies configuration settings.
- **Main Menu and Color Themes**: Displays the main menu and applies selected color themes.
- **Batch Launcher**: Gracefully handles missing `pwsh` or `powershell` executables.
- **Log and Error, Handling**: Handles log and error, messages to `.\errors.log`.

### PREVIEW:
- The New Main Menu is working...
```
========================================================================================================================
    Main Menu
========================================================================================================================








    1. Start Roleplaying

    2. Configure Roleplaying

    3. Configure Libraries

    4. Configure Colors








------------------------------------------------------------------------------------------------------------------------
Selection; Menu Options = 1-4, Exit Studio-Chat = X: :


```
- The Engine Window (old version)...
```
--------------------------------------------------------

Engine Initialized.
Loading menu.
Loaded: .\data\config.json
Accessed: Main Menu
Selected: Start Chatting
Loaded: .\data\response.json
Sending request to LM Studio...
Sending request to LM Studio (Attempt 1)...
Payload: {
  "messages": [
    {
      "content": "INFORMATION:\\nThe location is a Mountain, where, Wise-Llama and Wanderer, are present. Recently Wanderer and Wise-Llama noticed each other., and just now Wanderer said 'Hello llama, I brought beers, do llamas drink beer?' to Wise-Llama.\\nINSTRUCTION:\\nYou are functioning in the role of Ai Roleplay; Your task is, to respond as Wise-Llama to the communication from Wanderer, in one sentence involving an appropriate, short dialogue produced and single action taken, by Wise-Llama.\\nEXAMPLE OUTPUT:\\nai_npc_current: '\"I'm delighted to see you here, it's quite an unexpected pleasure!\", Wise-Llama says as they offer a warm smile to Wanderer'.",
      "role": "user"
    }
  ],
  "model": "Undi95/Llama-3-Unholy-8B"
}

...etc...

```

## REQUIREMENTS:
- Powershell Core 7, may specify 7.5 later, 7.5 is interesting..  
- LM Studio (Windows, Linux, Mac).

### INSTALLATION:
1. Install LM Studio, and ensure you have suitable models loaded...
2. Extract StudioChat to a suitable folder, for example, `D:\Programs\StudioChat`.
3. Run the launcher "StudioChat.Bat", configure settings in menu.
4. Start the Chat interaction, input `b` to return to the menu.

## NOTES:
- This project is intended a better version of the llama 2 style chatbot I made for WSL, for proof of a AI on powershell/lm studio concept; but when its done, do I make a, adventure game or agent/assitant or personal manager, out of it, what is the next stage after project completion??

### ARCHIVED DEVELOPMENT:
1. Consolidation functions require to be separated into individual functions for, "recent_events" and "session_history", so that they update on the screen individually, either that or merged with the function for processing converse, and add lines to, save to the key and redraw the menu, after each one within the function.  
2. When Starting the app, I am seeing some kind of error, the error is because certain things are not initialized yet, so, something is being called before its ready, everything else works, just need to isolate the instance and delete the call. Make a quick fix, like we did with the other one, start with 0, print message, put to 1, when 1 do function.
- Not doing for next release...
1. named pipe communication was a 2 day AI programming hell, and it ended up a complete waste of time, even with extensive test scripts. I have run xp anti-spy and oo-shutup, or some other thing, so?!?! maybe I broke named pipes is a factor. We are sticking with tcp!
- Done for next release....
1. Nothing yet.
- After completion of v1.0, then clone for other projects, such as a game.....
1. 1 Window for Random Static Text Map Generation, with 4 biomes the user will be able to roam to the limits of the map, there will be a NPC randomly located on the map, and the user will visit them to initiate the phase of roleplaying. 
2.  4 Roaming NPCs, where the characters will be Enumerated from name list file, also containing a gender assigned to each name, out of 3 possible genders. There will be less details in the user configuration page.
3. As no AI NPC config there, hence possibly an additional detail in the configuration page, assigning gender, and add gender to the wordlists, this would be inserted into the converse.txt, as well as possibly another detail, how someone would describe their character in 2 words, for example, 'grumpy recluse'.
1. Some kind of model for Image Generation, then use playground mode on LM Studio, then add a new graphical window taking up quarter screen for Graphics output, this should be based on "recent_events". Possibly when the player selects exit, then it would generate a final image from session history, and display it to the player as the program shuts down other windows, then close itself?? Maybe save scenario picture option? dunno. Either way it would require removal of the history in the display.
1. In theory, there could be some kind of text generated world map in a new window taking up a quarter of the screen, the player will there have options of locations to go to, the npc could be randomised based on the theme of the location, the user can at any point travel elsewhere, to meet a different person at the other location, or even at most of the locations there would be no people, so as for the user to have to search around for people. 
3. In theory, scenario_history would be able to be consolidated into "total_history" for all locations in the gaming session, and total_history could be used to customize future scenarios, so that they are themed towards what the player wants to find, hence the game could adapt towards what kinds of, scenarios and characters, preferred by the player, therein creating a theme of world, maybe, these themes could be saved or persistent until new game, enabling a continue option if there is history for it?? 
4. In theory, The player could also enter physical details, like, height and body type and gender, and this could influence the scenarios, logically requiring the, height and body type and gender, to be generated for the NPCs, and this could be considered in the prompt sent to the model for interaction. Possibly the ai could also psychologically analyze the total_history, and come up with a character sheet for the player, in addition to the pre-defined, height and body type and gender and name. 

### RESEARCH:
- Useful Models; https://huggingface.co/models?sort=trending&search=LLama-3-8b-Uncensored+gguf , one from here should be unfiltered, frank seems to work ok. There are no normal Llama 3 Chat Uncensored 8B GGUF currently, which is limiting production of Llama 3 unfiltered 8B gguf models. Noteworthy is Qwen-2 model, beating Llama 3 and producing GPT4 quality output, thereabouts, I am getting "Dolphin Qwen2 7B 6Bit" - https://huggingface.co/cognitivecomputations/dolphin-2.9.2-qwen2-7b-gguf. Relevantly the preset for Qwen, not sure if it works with Qwen2 - https://github.com/aj47/lm-studio-presets/blob/main/qwen.preset.json .
- Powershell 7.5 Beta, PowerShell Core beta updates can significantly enhance a local model chatbot by improving data handling with ConvertTo-Json serialization of BigInteger, providing actionable error suggestions, and adding a progress bar to Remove-Item. Enhanced path handling, early resolver registration, and improved error formatting boost stability and usability. Process management fixes allow better credential handling without admin privileges and easier process monitoring, while improved stream redirection enhances integration with native applications. These updates collectively enhance robustness, efficiency, and user experience for local model chatbots.

## DISCLAIMER:
This software is subject to the terms in License.Txt, covering usage, distribution, and modifications. For full details on your rights and obligations, refer to License.Txt.
