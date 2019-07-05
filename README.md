# Discord-Webhooks-from-Twitch
Get notifications in Discord when events happen at Twitch.tv

needed:
Twitch.tv account
Discord account
ifttt.com account

Connecting Twitch to ifttt.com is pretty simple, but getting the Webhooks in Discord to understand the information coming in is not streight forward. It requires some specific selections and Json to deliver properly.

Adding a message to Discord when your stream goes live

1. In Discord, go to your Channels "Server Settings" and then "Webhooks" to create a new webhook connected to the channel you want messages to go to. Copy the Webhook URL to be used in the next step.

2. In ifttt click the big "If This" and sellect Twitch and choose the "If New Sream Started..." Applet. Paste Discords Webhook into the URL section, choose Method: POST, and Content Type APPLICATION/JSON. 

3. In the Applet body section place the JSON code below. Edits can be made to the code, you can add more text and info to your post. Follow the template below as a guide and look for Discords CSS for tips on what you can and cant add.

BODY:
{ "content": "{{ChannelName}} went live on Twitch", "embeds": [{ "title": "{{ChannelUrl}}", "url": "{{ChannelUrl}}", "color": 6570404, "footer": { "text": "{{CreatedAt}}" }, "image": { "url": "{{StreamPreview}}" }, "author": { "name": "{{ChannelName}} is now streaming" }, "fields": [ { "name": "Playing", "value": "{{Game}}", "inline": true }, { "name": "Started at (streamer timezone)", "value": "{{CreatedAt}}", "inline": true } ] }] }

