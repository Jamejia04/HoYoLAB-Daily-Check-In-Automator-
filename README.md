<h1 align="center">
    HoYoLAB Auto Check In 
</h1>

A free script that automatically collects HoYoLAB daily check in rewards.
Supports all HoYoverse games. Can configure for multiple accounts

## Setup
1. Go to [Google Apps Script](https://script.google.com/home/start) and create a project with any name.
2. Select the editor and paste the code( [](https://github.com/canaria3406/hoyolab-auto-sign/blob/main/src/main-discord.gs)). Refer to the instructions below to configure the config file and save it.
3. Select "main" and click the "Run" button at the top.
   Grant the necessary permissions and confirm that the configuration is correct (Execution started > completed).
4. Click the trigger button on the left side and add a new trigger.
   Select the function to run: main
   Select the event source: Time-driven
   Select the type of time based trigger: Day timer
   Select the time of day: recommended to choose any off-peak time between 0900 to 1500.

## Configuration

```javascript
const profiles = [
  {
    token: "ltoken_v2=v2_CANARIAXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX3406; ltuid_v2=26XXXXX20;",
    genshin: true,
    honkai_star_rail: true,
    honkai_3: false,
    tears_of_themis: false,
    zenless_zone_zero: false,
    accountName: "YOUR GAME NAME"
  }
];
```

<details>
<summary><b>HoYoLAB settings</b></summary>

1. **token** - Please enter the token for HoYoLAB check-in page.

   Refer to [https://github.com/Joshua-Noakes1/mei-cards#2-getting-your-hoyolab-cookies](https://github.com/Joshua-Noakes1/mei-cards#2-getting-your-hoyolab-cookies) for obtaining the ltoken_v2 and ltuid_v2. 
   After obtaining the ltoken_v2 and ltuid_v2, paste into the "quotes".
   

2. **genshin**

   Set to true if enabling auto check in for Genshin Impact. Otherwise, set to false or delete this line. 

3. **honkai_star_rail**

   Set to true if enabling auto check in for Honkai Star Rail. Otherwise, set to false or delete this line.  

4. **honkai_3**

   Set to true if enabling auto check in for Honkai Impact 3rd. Otherwise, set to false or delete this line.  

5. **tears_of_themis**

   Set to true if enabling auto check in for Tears of Themis. Otherwise, set to false or delete this line.  

6. **zenless_zone_zero**

   Set to true if enabling auto check in for Zenless Zone Zero. Otherwise, set to false or delete this line.  

7. **accountName** - Please enter your customized in game name.

   Please enter your HoYoLAB or in-game name here.

</details>

<details>
<summary><b>discord notify settings</b></summary>

```javascript
const discord_notify = true
const myDiscordID = "20000080000000040"
const discordWebhook = "https://discord.com/api/webhooks/1050000000000000060/6aXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXnB"
```

1. **discord_notify**

   To enable Discord notifications.
   If you discord notifications, set to true. If not, set to false.

2. **myDiscordID** - Enter your Discord user ID.

   To ping when there is an unsuccessful check-in.
   Copy your Discord user ID which will look like `23456789012345678` and fill it in "quotes".
   Refer to [this article](https://support.discord.com/hc/en-us/articles/206346498) to find your Discord user ID.
   If you don't want to be pinged, leave the "quotes" empty.

3. **discordWebhook** - Please enter the Discord webhook for the server channel to send notify.

   Refer to [this article](https://support.discord.com/hc/en-us/articles/228383668) to create a Discord webhook.
   When finished creating the Discord webhook, you will receive your Discord webhook URL, which will look like `https://discord.com/api/webhooks/1234567890987654321/PekopekoPekopekoPekopeko06f810494a4dbf07b726924a5f60659f09edcaa1`.
   Copy the URL and paste it in "quotes".

</details>

## Demo
If the auto check in process is success, it will send "OK".
If you have already check in today, it will send "Traveler/Trailblazer/Captain, you've already checked in today"

<details>
<summary><b>Single HoYoLAB account auto check-in with Discord notification.</b></summary>

```javascript
const profiles = [
  {
    token: "account_mid_v2=123xyzabcd_hi; account_id_v2=26XXXXX20; ltoken_v2=v2_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX3406; ltmid_v2=123xyzabcd_hi; ltuid_v2=26XXXXX20;",
    genshin: true,
    honkai_star_rail: true,
    accountName: ""
  }
];

const discord_notify = true
const myDiscordID = "240000800000300040"
const discordWebhook = "https://discord.com/api/webhooks/10xxxxxxxxxxxxxxx60/6aXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXnB"
```

</details>