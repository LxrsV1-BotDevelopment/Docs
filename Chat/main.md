# Chats

## Sending message to a player:

```typescript
// this needs to be in a command class

const sender = context.getSource() as Player;
await sender.sendMessage('YOUR MESSAGE');
```

## Register a new command
```typescript
// <command_name> -> name of your command (if name would be mycommand, you will have to type /mycommand )
// <namespace> -> project name

await this.api.getServer().getCommandManager().registerClassCommand({
      id: "<namespace>:<command_name>",
      description: "",
      register: async (dispatcher: CommandDispatcher<any>) => {
        dispatcher.register(
          literal("<command_name>").executes(async (context: CommandContext<any>) => {
            // code when the command get executed
            // if you want to send a message to the user check the box above
          })
        )
      },
      execute: async (sender: Player, args: any[]) => { 
        // this part isn't done yet, leave it empty (execute is required, if you don't use it it'll give errors)
      }
    });
```

