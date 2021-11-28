# Renpy Discord Rich Precense

A repository with the necesary files to setup a Discord Rich Precense in your Renpy game.

# How to setup

Add the "python-packages" folder in your base game directory, then add the next lines in your "screens.rpy". Check the line 355 of [screens.rpy](screens.rpy).

```python
init python:
    import time
    initial_time = time.time()

screen main_menu():
    #discord
    python:
        import discord_rpc
        discord_rpc.initialize('ID')
        discord_rpc.update_connection()
        discord_rpc.update_presence(
            **{
                'details': 'TEXT EXAMPLE',
                'start_timestamp': initial_time,
                'large_image_key': 'IMAGE EXAMPLE'
            }
        )
        discord_rpc.update_connection()
```