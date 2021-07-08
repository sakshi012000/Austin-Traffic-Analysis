# Educational Chatbot
<div align="center">

  ![](https://www.userlike.com/api/proxy/resize/do-i-need-a-chatbot/header-chat-box.png?height=720)

</div>

---

<p align="center">AI Educational Chatbot</p>

# Table of Contents
+ [Rasa bot on local system](#Rasa_bot_on_local_system)
+ [Deployments steps](#Deployments_steps)
+ [Customization](#Customization)

## Rasa bot on local system: <a name="Rasa_bot_on_local_system"></a>
+ Python Version: 3.7
+ Steps:
+ Move to the directory ras.
 ```
 $ conda activate rasa
```
+ This will set the rasa environment.
 ```
 $ rasa train
```
+ This will train the rasa model.
 ```
 $ rasa run actions
```
+ This will run the actions file.
 ```
 $ rasa run -m models --enable-api --cors "*" --debug
```
+ Inside the same directory ras run the following command to enable API.
+ Now open the index.html file from the Rasa_CustomUI-v_2.0 folder to access the chatbot.



### Deployments steps: <a name="Deployments_steps"></a>
+ Create a new environment using conda. Activate it using conda activate env_name.
+ Run:
 ```
 $ pip install -r requirements.txt
```
1. In app.py, set host = “0.0.0.0”, set port number, set debug to False
2. In ras/credentials.yml, change url from localhost to VM’s IP address.
3. In ras/endpoints.yml, change url from localhost to VM’s IP address.
4. In static/js/script.js, change url in ajax call to VM’s IP address,
5. In ras/ run rasa run actions
6. In a new prompt, cd ras followed by rasa train. In same prompt run: 
 ```
 $ rasa run -m models --enable-api --cors "*" --debug
```
7. In new prompt, run:
 ```
 $ python app.py
 ```
 
## Customization <a name="Customization"></a>
1. Add more questions in nlu.yml to get a more robust model
2. To modify/replace scraper, look at ras/actions
3. If you add more intents in the nlu.yml file, update the stories.yml file and domain.yml file and actions.py file
4. Add as many stories as possible in stories.yml to get the bot work and understand properly with both happy and sad path.


+ This is a educational chatbot made up by customizing rasa.
