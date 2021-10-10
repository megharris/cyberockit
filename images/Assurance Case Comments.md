Add comments here for each other's assurance cases.

**Dylan's Comments**

 1. Jay's Assurance Case - 
   For Rebuttal R3, by a "secure IP" do you mean the connection to the IP is secure?
    Sub-Claim C5 is also a little vague, how does the "secure application" give remote access? I see in Evidence E1 that      DuckDNS is used, but how does that relate to a secure remote access?
    I would change the wording on Sub-Claim C6 to "HA prevents brute force attacks with ...". While this is a complete noun-phase it feels like it needs to be a litte  more explained.
    Great job on the Assurance Case!
    
 2. Meg's Assurance Case - 
    Need to remove the string from Inference Rule IR1 down, as it is from Dr. G's original sample.
         Meg's response: Just uploaded early so team could review the bulk of the project, I still had to finish this. Thank you.
    Rebuttal R3 has a conjunction in it. Remove the "and expiration time is too long" and make a new Rebuttal. This is the  same for Sub-Claim C6.
         Meg's response: Updated. THANK YOU!
    Sub-Claim C5 also has a conjunction in it. Remove "and validates against response manipulation" and either fork the line or remove it. 
         Meg's response: Updated. THANK YOU!
    All three undermines have the same UM number (UM1)
         Meg's response: Updated. THANK YOU!
    I dont know if you need to include all three undermines as the evidence they are undermining is already hard-coded into HA. Since all of them have the same answer and final evidence, the ends of the strings look redundant. 
         Meg's response: Agreed. REmoved all but 1. Thank you!
    This is a very well thought out assurance case! Good job!
         Meg's response: Thanks, Dylan!
    
 3. Noah's Assurance Case - (comments are for V5)
    In Sub-Claim C9 take out "should", it adds ambiguity and is informal. The evidence is given below it to show that this is not an ambiguous statement.
    In Sub-Claim C5 take out "and" and replace with "or". The current wording sounds like both threshold and settings have to be changed in order to notify the user, when you go on to show that it is either threshold or the settings.
    Great job on the progressions of the assurance cases, and on the part 2 stuff. 
    
 4. Shifat's Assurance Case -
    For Top-Claim C1 take out "mostly free" and replace with "minimize". Current wording is too informal.
    In Sub-Claim C4 take out "mostly". It is too informal, and is ambiguous. You supply evidence after the claim to show that it is not ambiguous. 
    Sub-Claim C3 needs to be branched out to two or three different Sub-Claims. With three conjections separating three points in the claim, each point needs to have its own claim. The Evidence supporting each claim can be the same, but branching them out is what Dr.G stated he wanted.
    Great job on the case so far! The line of reasoning is sound, the graph just needs a few struncture tweeks. 

**Jay's Comments** 
<br/> Meg –

1.	You can reword top level claim. Format should be ‘application’ ‘does something’ ‘to something’. For example – HA provides secure user profiles. 
     1. Meg's response: per Dr. G, top claim can't be so absolute. I have changed it to say "HA minimizes risk of misusers accessing valid-user profiles."
2.	Inference rule should start with ‘if’. For example – If HA ‘does something’ then ‘something can be inferred’.
     1. Meg's response: I've corrected this. As mentioned when uploading, I was not finished with the inference and still need to think on it. That's why there were still tweety references in it. Thank you.
3.	Check undercut C1 and Subclaim C6. It is from tweety example of Dr. Gandhi.
     1. Meg's response: Again, this was not completed at the time of upload.
4.	Spelling correction of ‘assistance’ in subclaim C3.
     1. Meg's response: corrected, thank you.
5.	Sub-claim C2 – ‘in second way’ can be dropped as the sentence would make same sense after that.
     1. Meg's response: changed to "with multiple methods" - trying to show that MFA is more than one authentication method. Thank you.
7.	Rebuttal R3, subclaim C6, subclaim C5 – avoid use of ‘and’.
     1. Meg's response: THANK YOU! Updated all.


**Noah's Comments**
1. It looks like we may want to establish how we refer to Home Assistant as a group. Some say just HA or Home Assistance rather than Assistant. If we decide how to refer to it as a group, it will look more uniform. 
      1. Meg's Response: AGREE!! Let's all just use HA because even in some instances it's been called "Home Assistance" instead of "Home Assistant" so let's just be consistent.
3. Another group thing that we can look at, some are numbering each item from right to left or bottom to up. In Dr. G's example, it looks like the numbering goes from left to right and is generally bottom down as you go along, so we could unify that as a group too. We'll just have to be mindful of how this effects the evidence section.
      1. I can true this up when we're all done.

Overall it's looking great everyone!

**Meg's Comments** 

<br/> Noah –

1.	Reword top level claim: "HA minimizes risk of misuser control of IoT devices"
2.	Reword c3: "....connecting to previously connected IoT devices"
3.	c5: "user is quickly notified when device settings are changed"
4.	c8: "HA alerts are enabled by default"
5.	evidence has to be a noun, so e5: "default settings"
6.	I'm confused by the bluetooth branch. R5 seems to be saying that if the devices are not bluetooth, then they're safe from control by misusers. Can any device connect to HA without bluetooth?
7.	E3: "failed-connection test results"
8.	c9: "IoT device bluetooth connection requires proximity"
9.	e6: where is this documented usually? Is it in the configuration.yaml? If so, just put that in e6. You could change c9 to say "Iot device bluetooth connection requires 10 meter proximity" and then e6 says "configuration.yaml"
10.	e4: take out the word "available

<br/> Dylan - 

1. Top claim can't be so absolute. Change wording to (this or something similar): "	HA minimizes risk of misuser control of IoT devices" NOTE: this is the same wording as the top claim for Noah but I think since you're both approaching it differently, it's ok to use. I'd be happy to check with Dr. G if you're uncomfortable with this but I believe this is the way to go.
2. IR1: I think Inference is misspelled. Hard to tell if it's a blip on my screen or if  it's got two I's
3. C5: reword as "Optionally enabled TCP integration verifies communication to appropriate devices"
4. I don't think e3 is really good evidence of C5. It seems like e3 is saying that 'UDP is default because not all devices can use TCP' which may be true but I don't think that's evidence for the fact that 'TCP ensures communication goes to the correct device" which is the purpose of c5. Right? I think you're focusing on the "option" part of c5 instead of the TCP part which is what the branch is really getting at.
5. We can't word things in terms of what the users or system "can" do or "should" do but what "is done" so c3: "HA only accepts connection with authenticated devices"
6. Evidence has to be nouns only. So E1: "Nest Documentation"
7. e2: I think this is a noun but i have a gut feeling he'll tell us it's too verbose. Maybe shorten it to: "source code documentation"
8. c4: address is misspelled.

<br/> Jay - 

1. I don't think the top claim should be so absolute, per our meeting with Dr. G on Thursday but I'm having trouble rewording it. Any ideas?
2. E1: reword to "DuckDNS" - there's no need to mention when it was introduced. It's there now. 
3. e5: reword to "IP_bans.yaml configuration file"


<br/> Shifat -

1. GOOD!!! I don't have any comments - I could obviously be missing things but it looks logical to me!

**Shifat's Comments**

I have read through the previous comments and all the questions I had, was already mentioned. Other than that it all looks good to me.
