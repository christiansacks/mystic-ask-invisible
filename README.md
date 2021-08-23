# mystic-ask-invisible
If you want to offer users the option of logging in invisible, but not on their first call of the day, this should sort you out.

## configuration

1. In mystic -cfg, in the Configuration->Login/Matrix dialog, set Invisible ACS to something high, like **s50** This will be the ACS that will be allowed to be invisible, and the ACS will will temporarily upgrade users to if they are allowed to use Invisible mode.
![image](https://user-images.githubusercontent.com/40481087/130405729-6b084423-aaa9-4707-9c09-6cc980528cbc.png)
2. Make sure you have s50 (or whatever you chose in #1) defined in Editors->Security Level Editor.
![image](https://user-images.githubusercontent.com/40481087/130405805-e91fc6a4-4e7d-4141-9be7-48eac08fa997.png)
3. Copy or Symlink ml-askinvisible.mpy to /mystic/scripts directory

Make a new prelogin entry like this;

```
Command    | (GY) Execute Python 2 Script
Data       | /mystic/scripts/ml-askinvisible.mpy
Access     | s30!s50
Grid Event | Selected
```

In the above example, I have chosen to allow users with s30 and above (upto s50) to get offered the choice to go invisible using this script, and if the user is s50 and above they will just be asked to go invisible by the Mystic built in.


That just about wraps it up for this one.
