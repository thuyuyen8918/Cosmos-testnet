## Briefly Introduction
- This guide is used to setup simplified alerting system to foward error/warning to your Telegram group and your email.

## Setup part
### Create Telegram bot 
- Using [@BotFather](https://t.me/BotFather) to create your BOT, then store HTTP API of your BOT carefully
![image](https://user-images.githubusercontent.com/109055532/192514277-03c711ec-39b3-44e9-8e08-18fc75c06d44.png)

- Set environment variable for your API BOT
```
echo export TG_API='5356867103:AAFicbMvs20R_5vFpWQ88qocT-e0y38P5LM' >> $HOME/.bash_profile
source $HOME/.bash_profile
```
- Create your own Telegram group, then add the bot to the group as Administrator, send a message in your Tele group.
- Set environment variable for chat ID of your Tele group
```
TG_ID=$(curl -s https://api.telegram.org/bot$TG_API/getUpdates| jq | grep "\"id\"" |tail -n 1 |awk '{print $2}' | tr -d ",")
echo export TG_ID=$TG_ID >> $HOME/.bash_profile
source $HOME/.bash_profile
```
- 
