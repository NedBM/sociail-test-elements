
The feature I decided to implement is adding optional skills to the user profile within the settings page. I first implemented a basic version within the UserPersonalInfoSettings.tsx, I thought this would be a good place for the feature to live below other settings such as name, email, and phone number. 


I noticed I would need to use the client.ts for the data to persist so I added the necessary code to client.ts to add and remove skills as needed. I added the basic interface for the skill name and id and added the functions within the class of the Matrix client to make the data persist within the client. 

Within the UserPersonalInfoSettings.tsx the component was importing AddRemoveThreepids.tsx to handle rendering and the phone number and email inputs. I decided to build out the Skills feature within a separate component but use the building blocks that the Threepids.tsx was using to handle the input, button and loading. This was helpful for the feature to look natural within the settings page and follow similar practices that the project was already using. Here is a quick demo video of the feature.


Some basic improvements that I would want to add include:
Adding an extra modal to confirm removal 
Adding a combobox or auto typing as you type in the skill you want to add if it is a commonly selected skill
Adding a color pallet to similar skills such as a blue for developer or IT or yellow for PM role.


https://github.com/user-attachments/assets/38922e08-3e04-439e-8488-95b1ac864f6b

