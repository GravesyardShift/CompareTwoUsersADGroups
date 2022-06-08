# CompareTwoUsersADGroups
- Very simple PowerShell script that compares and returns the groups two users have in common and differences

## Instructions
- Open with PowerShell
- When prompted, enter the user id of the first employee you want to check permissions of. (See below if you need help finding what user id format your organization uses)
- When prompted enter the second user's id.
- The script will take a couple seconds to retrieve the information from Active Directory
- It will return three lists, one for groups that both users share, one for the groups unique to the first user, and one for the groups unique to the second user.
- Press enter to quit.


## Finding the user id's for your organization
- Open Active Directory
- Right click on company organization
- Click on "Find..."
- In the "Find Users, Contacts, and Groups" box, search the name of the person who's user id you want to find.
- Double-click on the user
- In the "Account" tab, under the "User Logon Name (pre-Windows 2000)", in the right box, will be their user id.
