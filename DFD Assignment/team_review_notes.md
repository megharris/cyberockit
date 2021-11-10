**Dylan's Comments**
     
     Shifat
-	You may want to change the name of the trust boundary that is in front
     of the Application Provider from “Unknown Developer” to “App Store Boundary”.
     While “unknown developer” is accurate with the background knowledge of your 
     use case, it is a bit ambiguous.
     
     Jay
-	Drawing needs to be done in MTMT per Dr. G’s requirements
-	Change “Add-ons example VLC” to “Optional Applications”, Add-ons is a 
     bit ambiguous for the entity.
-	For the “Memory” data flow, is this just the part of the a running HA 
     optional application that is currently running in memory? You may want 
     to make the name more defined.
     
     Noah
-	You’ll want to change the name of the data flow that connects the User to HA.
     “Secure Access” is a noun phrase but adding “log-in” to it would help clarify
     what action it is that the user is doing to HA. 
     
     Meg
-	Im not sure if “1.0 Home Assistant” and “1.1 Update Profile Credentials” are 
     running in different memory parts at execution. If they are not, then they 
     could be in the same Process bubble. 
-	I do think that your trust boundaries are correct for the user and the MFA 
     database. I know you voiced concern about that previously. I do not believe
     you need one for the Transaction Database as that database is just acting 
     as a repository for the transactions, not being checked against like the 
     MFA Database is.

**Noah's Comments**

     Dylan
     I may be wrong but the database block looks different from the regular database
     items in the lecture, which usually have a two horizontal lines but no vertical 
     lines. Boundary is also misspelled in your trust boundary. 
     
     Meg
     You might be able to expand the data flow for 'invalid credentials', maybe I am 
     incorrect but the data actually being sent may not be the credentials themselves
     but rather a flag value or something else. Again not sure on that but it may not
     actually send over the invalid credentials
     
     Shifat
     You might be able to add another trust boundary between the user and the HA app,
     and it looks like the database block is different than in lecture. The ones in 
     the lecture only have two horizontal lines and no vertical lines. You might be 
     able to reword your trust boundary for the developer boundary to something like
     'External Development/Developer Boundary'. 
     
     Jay
     You might look at changing both data flows called 'data information' to more 
     descriptive data flows. You have one labeled for a data request and one for a 
     data response. Describing what data is responding from the database and what
     data is requesting in the Add-ons might help. Let me know if you'd like me to 
     finalize your diagram on TMT once you make changes since you don't have access. 
