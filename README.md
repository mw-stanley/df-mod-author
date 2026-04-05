# Dwarf Fortress Mod Author Skill

This skill is a tool to help you create and edit mods for Dwarf Fortress.

Add this skill to your agent so it can understand the structure of Dwarf Fortress mods, RAW files, and tokens and arguments used in them.

You can see an example of the skill in action here: https://gist.github.com/mw-stanley/a6017233be672e05de8f18f122c6910f

## Update information

- This skill is current as of Dwarf Fortress version 53.11.
- If you're using a newer version of Dwarf Fortress, there may be token changes that are not documented in the skill. 
- If the skill is outdated, the agent should attempt to use the vanilla files to determine the correct tokens and arguments, but it may not always succeed.

## Teaching the Agent where to find the vanilla files

- The skill will try to reference the vanialla raws to validate, avoid hallucinations, and to use as a base.
- The agent should prompt you to confirm the location of the vanilla files if it cannot find them. 
    - It will attempt to save the location in its memory if your client has that feature. 
    - You can add your own instructions to your AGENTS.md file to tell it where to find them instead.
- Security is important when using agents - don't give it write access to your whole computer.
    - You can give the agent read access to the vanilla files in the game directory - by default it will try to find the game directory and read from it.
    - Make sure if you give it access to the game directory, that you're only giving it read access and only to that directory. Use the sandbox features of your client to make sure it's restricted properly.
    - You may want to make a copy of the vanilla raws for the agent to use and point it there instead.

## Advice for Usage

### Working with the agent

- Start with planning mode - the DF raws are complex and letting your agent plan first will help it gather relevant material and make sure it "understands" the task before it starts editing.
- Watch the context size - some of the DF raw files are pretty big and you may be trying to load a lot of them. Tell the model in planning mode to be selective about what it loads. This can also avoid long API calls and timeouts.
- Use a powerful model with reasoning - the DF raws can require a lot of reasoning to get right. Claude has a model called `opusplan` that uses Opus to plan and Sonnet to execute that can be useful.
- I prefer to use the CLI to run the agent with this skill - I have tested with the `gemini` and `claude` CLIs. You can use the CLI in conjunction with an IDE like VSCode, Antigravity, or Cursor. 

### Validating & Troubleshooting

- The agent should be pretty good about not hallucinating tokens or arguments, but it's not perfect. 
- The agent should be able to validate its own work by checking the vanilla raws and the instructions in this skill - tell it to do so if it hasn't.
- Make changes in small steps and validate them in-game to isolate issues and then ask the agent to fix them.
- Tell the agent to explain its reasoning to you if you think it might have made a mistake.
- If the agent is having trouble with a task, try breaking it down into smaller steps and asking the agent to complete each step individually - planning mode is great for this.

## Feedback and improvements

Please feel free to open an issue or submit a pull request to suggest improvements or report problems.

### Discord

You can join the Kitfox Games Discord to chat with other modders and get help with your mods. Please note that this is a community server and not directly affiliated with the developers of this skill.

Members of the community will not be very tolerant of being asked to clean up after an AI agent that has made a mess of things. Get the agent to help you first.
