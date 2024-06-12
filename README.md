# StudioChat
Working, not finished. Powershell-Core Multi-Window Chatbot with LM Studio hosted model(s). 

### DEVELOPMENT NOTES..
- V1 can be done in the next 24hrs, objectives, "better than my previous chatbot" and "all noticable bugs fixed"...
1. While starting a mode of roleplay, it seems to send the starting text to the model, as if the user just inputted it, for which, the output from the model is then ignored. if there is no input on the prompt for "Your Input (Back=B, Exit=X):", then the program should be doing nothing but waiting for input; it should NOT be doing ANYTHING with lm studio, while in the processes of starting roleplay mode.
- After completion of v1.0, then possibly...
1. Some kind of model for Image Generation, then use playground mode on LM Studio, then add a new graphical window taking up quarter screen for Graphics output, this should be based on "recent_events". Possibly when the player selects exit, then it would generate a final image from session history, and display it to the player as the program shuts down other windows, then close itself?? Maybe save scenario picture option? dunno. Either way it would require removal of the history in the display.
1. In theory, there could be some kind of text generated world map in a new window taking up a quarter of the screen, the player will there have options of locations to go to, the npc could be randomised based on the theme of the location, the user can at any point travel elsewhere, to meet a different person at the other location, or even at most of the locations there would be no people, so as for the user to have to search around for people. 
3. In theory, scenario_history would be able to be consolidated into "total_history" for all locations in the gaming session, and total_history could be used to customize future scenarios, so that they are themed towards what the player wants to find, hence the game could adapt towards what kinds of, scenarios and characters, preferred by the player, therein creating a theme of world, maybe, these themes could be saved or persistent until new game, enabling a continue option if there is history for it?? 
4. In theory, The player could also enter physical details, like, height and body type and gender, and this could influence the scenarios, logically requiring the, height and body type and gender, to be generated for the NPCs, and this could be considered in the prompt sent to the model for interaction. Possibly the ai could also psychologically analyze the total_history, and come up with a character sheet for the player, in addition to the pre-defined, height and body type and gender and name. 

## FEATURES:
- 2 Windows, Engine and Chat, snapping to each corner of the screen on launch.
- 1 Window to come...Image Generation based on "recent_events", ie previous actions.
- Multi-OS Mac/Linux/Windows compatibility thanks to, PS Core and LM Studio.
- GPU/CPU interference, and many other great features due to LM Studio.
- IDK TBA

### PREVIEW:
- Chat Window...
```
========================================================

Wanderer:
Oh, a llama, say, you look like a very wise llama, do you have wise thoughts and do wise things?

--------------------------------------------------------

Wise-Llama:
'"Ah, yes, I do possess wise thoughts and wisdom from the ancient mountains, would you like to hear one"', Wise-Llama asks while nodding thoughtfully and producing a small, intricately carved wooden box from their cloak

--------------------------------------------------------

Recent Events:
Wanderer and Wise-Llama interacted, with the latter being perceived as wise by the former, who was impressed by their thoughtful demeanor and the presentation of a small wooden box from their cloak.

--------------------------------------------------------

Scenario History:
The roleplay started, and then Wanderer and Wise-Llama noticed each other.

========================================================

Your Input (Back=B, Exit=X):

```
- Engine Window...
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

### RESEARCH..
- Useful Models; https://huggingface.co/models?sort=trending&search=LLama-3-8b-Uncensored+gguf , one from here should be unfiltered, frank seems to work ok. There are no normal Llama 3 Chat Uncensored 8B GGUF currently, which is limiting production of Llama 3 unfiltered 8B gguf models. Noteworthy is Qwen-2 model, beating Llama 3 and producing GPT4 quality output, thereabouts, I am getting "Dolphin Qwen2 7B 6Bit" - https://huggingface.co/cognitivecomputations/dolphin-2.9.2-qwen2-7b-gguf.
- Powershell 7.5 Beta, PowerShell Core beta updates can significantly enhance a local model chatbot by improving data handling with ConvertTo-Json serialization of BigInteger, providing actionable error suggestions, and adding a progress bar to Remove-Item. Enhanced path handling, early resolver registration, and improved error formatting boost stability and usability. Process management fixes allow better credential handling without admin privileges and easier process monitoring, while improved stream redirection enhances integration with native applications. These updates collectively enhance robustness, efficiency, and user experience for local model chatbots.

## DISCLAIMER:
This software is subject to the terms in License.Txt, covering usage, distribution, and modifications. For full details on your rights and obligations, refer to License.Txt.
