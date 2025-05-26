# Beginner's Guide: Adding Custom Shells to NoLag Properties System

## Step 1: Prepare Your Custom Shell

Make sure you have:
- Your custom shell resource installed on the server
- Images of your shell for the realtor menu (exterior and interior shots)

## Step 2: Find Your Shell's Offset

1. Enable the offset finder in the NoLag Properties config:
   - Open `config.lua` in the NoLag Properties resource
   - Set `EnableOffsetFinder = true`

2. Use the in-game command to test your shell:
   ```
   /testshell [shellname]
   ```
   Replace `[shellname]` with the name of your shell (the hash name without the backticks)

3. Note down the offset values that appear in-game. These include:
   - x, y, z coordinates
   - h (heading)
   - width

## Step 3: Create the Custom Shell Configuration File

1. Navigate to the custom shells directory:
   ```
   nolag_properties/custom/shells/
   ```

2. Create a new Lua file (e.g., `myshells.lua`)

3. Use this template for your file:

```lua
CreateThread(function()
    local shells = {
        ["Your Shell Name"] = {
            label = "Your Shell Display Name",
            hash = `your_shell_hash`,  -- Use backticks around the hash name
            doorOffset = { 
                x = 0.0, -- Replace with your x offset
                y = 0.0, -- Replace with your y offset
                z = 0.0, -- Replace with your z offset
                h = 0.0, -- Replace with your heading
                width = 2.0 -- Replace with your door width
            },
            stash = {
                maxweight = 80000000,  -- Adjust storage capacity as needed
                slots = 120,  -- Adjust slot count as needed
            },
            imgs = {
                {
                    url = "https://yourwebsite.com/image1.png",  -- Replace with your image URL
                },
                {
                    url = "https://yourwebsite.com/image2.png",  -- Optional additional images
                },
            }
        },
        
        -- You can add more shells by adding additional entries here
    }

    -- This adds your shells to a category called "Custom Shells" in the menu
    InsertInteriors(shells, "Custom Shells")
end)
```

## Step 4: Customize Your Shell Configuration

Fill in the template with your specific shell information:

1. **Shell Name and Label**: Replace "Your Shell Name" with a unique identifier and "Your Shell Display Name" with the name that will show in the menu

2. **Shell Hash**: Replace `your_shell_hash` with your shell's actual hash (keep the backticks)

3. **Door Offset**: Replace the placeholder values with the offset values you found in Step 2

4. **Stash Configuration**: Adjust the storage capacity and slots based on your preference

5. **Images**: Replace the example URLs with direct links to your shell images
   - Host your images on an image hosting service
   - Make sure the URLs are direct links to the images

## Step 5: Add Multiple Shells (Optional)

To add multiple shells, duplicate the shell entry inside the `shells` table:

```lua
local shells = {
    ["First Shell"] = {
        -- First shell configuration
    },
    ["Second Shell"] = {
        -- Second shell configuration
    }
}
```

## Step 6: Testing Your Custom Shells

1. Save your `myshells.lua` file
2. Restart the NoLag Properties resource:
   ```
   /restart nolag_properties
   ```
3. Check the real estate menu to confirm your shells appear in the "Custom Shells" category

## Troubleshooting Tips

- **Shell not appearing**: Verify your Lua syntax is correct and the file is in the right directory
- **Offset issues**: Use the offset finder again to get more accurate values
- **Image not showing**: Check that your image URLs are direct links and publicly accessible

Remember to disable the offset finder in `config.lua` when you're done testing by setting `EnableOffsetFinder = false`.
