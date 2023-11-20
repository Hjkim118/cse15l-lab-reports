Part 1

A failure-inducing input for the buggy program, as a JUnit test and any associated code

```
@Test
  public void testReversedinput(){
    int[] input = {1,2,3};
    assertArrayEquals(new int[]{ 3,2,1 }, ArrayExamples.reversed(input));
  }
```

```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

An input that doesn’t induce a failure, as a JUnit test and any associated code

```
@Test
  public void testReversedinput(){
    int[] input = {1,2,3};
    assertArrayEquals(new int[]{ 3 }, ArrayExamples.reversed(input));
  }
```

```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

The symptom, as the output of running the tests

![Image](lab3_1_1.png)
![Image](lab3_1_2.png)

The bug, as the before-and-after code change required to fix it

before
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

After
```
// Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
```

This is because the before code it keeps does not swap the elements, it saves the arr[arr.length - i - 1] to arr[i] without returning arr[i] value to arr[arr.length - i - 1].
So, if we save arr[arr.length - i - 1] value to temp and return it to arr[i], the problems will be solved.

Part 2
I chose grep and command examples.

1. '-i' command
```
grep -i flights ./technical/911report/chapter-1.txt
```
```
INSIDE THE FOUR FLIGHTS
Boarding the Flights
    The 19 men were aboard four transcontinental flights.
    The hijackers attacked sometime between 8:42 and 8:46. They used knives (as reported by two passengers and a flight attendant), Mace (reported by one passenger), and the threat of a bomb (reported by the same passenger). They stabbed members of the flight crew (reported by a flight attendant and one passenger). Both pilots had been killed (reported by one flight attendant). The eyewitness accounts came from calls made from the rear of the plane, from passengers originally seated further forward in the cabin, a sign that passengers and perhaps crew had been moved to the back of the aircraft. Given similarities to American 11 in hijacker seating and in eyewitness reports of tactics and weapons, as well as the contact between the presumed team leaders, Atta and Shehhi, we believe the tactics were similar on both flights.
    American 77 pushed back from its gate at 8:09 and took off at 8:20. At 8:46, the flight reached its assigned cruising altitude of 35,000 feet. Cabin service would have begun. At 8:51, American 77 transmitted its last routine radio communication. The hijacking began between 8:51 and 8:54. As on American 11 and United 175, the hijackers used knives (reported by one passenger) and moved all the passengers (and possibly crew) to the rear of the aircraft (reported by one flight attendant and one passenger). Unlike the earlier flights, the Flight 77 hijackers were reported by a passenger to have box cutters. Finally, a passenger reported that an announcement had been made by the "pilot" that the plane had been hijacked. Neither of the firsthand accounts mentioned any stabbings or the threat or use of either a bomb or Mace, though both witnesses began the flight in the first-class cabin.
    At 9:00, American Airlines Executive Vice President Gerard Arpey learned that communications had been lost with American 77. This was now the second American aircraft in trouble. He ordered all American Airlines flights in the Northeast that had not taken off to remain on the ground. Shortly before 9:10, suspecting that American 77 had been hijacked, American headquarters concluded that the second aircraft to hit the World Trade Center might have been Flight 77. After learning that United Airlines was missing a plane, American Airlines headquarters extended the ground stop nationwide.
    The hijackers had planned to take flights scheduled to depart at 7:45 (American 11), 8:00 (United 175 and United 93), and 8:10 (American 77). Three of the flights had actually taken off within 10 to 15 minutes of their planned departure times. United 93 would ordinarily have taken off about 15 minutes after pulling away from the gate. When it left the ground at 8:42, the flight was running more than 25 minutes late.
    The airlines bore responsibility, too. They were facing an escalating number of conflicting and, for the most part, erroneous reports about other flights, as well as a continuing lack of vital information from the FAA about the hijacked flights. We found no evidence, however, that American Airlines sent any cockpit warnings to its aircraft on 9/11. United's first decisive action to notify its airborne aircraft to take defensive action did not come until 9:19, when a United flight dispatcher, Ed Ballinger, took the initiative to begin transmitting warnings to his 16 transcontinental flights: "Beware any cockpit intrusion- Two a/c [aircraft] hit World Trade Center." One of the flights that received the warning was United 93. Because Ballinger was still responsible for his other flights as well as Flight 175, his warning message was not transmitted to Flight 93 until 9:23.
    The terrorists who hijacked three other commercial flights on 9/11 operated in five-man teams. They initiated their cockpit takeover within 30 minutes of takeoff. On Flight 93, however, the takeover took place 46 minutes after takeoff and there were only four hijackers. The operative likely intended to round out the team for this flight, Mohamed al Kahtani, had been refused entry by a suspicious immigration inspector at Florida's Orlando International Airport in August.
    At least two callers from the flight reported that the hijackers knew that passengers were making calls but did not seem to care. It is quite possible Jarrah knew of the success of the assault on the World Trade Center. He could have learned of this from messages being sent by United Airlines to the cockpits of its transcontinental flights, including Flight 93, warning of cockpit intrusion and telling of the New York attacks. But even without them, he would certainly have understood that the attacks on the World Trade Center would already have unfolded, given Flight 93's tardy departure from Newark. If Jarrah did know that the passengers were making calls, it might not have occurred to him that they were certain to learn what had happened in New York, thereby defeating his attempts at deception.
    Passengers on three flights reported the hijackers' claim of having a bomb. The FBI told us they found no trace of explosives at the crash sites. One of the passengers who mentioned a bomb expressed his belief that it was not real. Lacking any evidence that the hijackers attempted to smuggle such illegal items past the security screening checkpoints, we believe the bombs were probably fake.
    Another commercial aircraft in the vicinity then radioed in with "reports over the radio of a commuter plane hitting the World Trade Center." The controller spent the next several minutes handing off the other flights on his scope to other controllers and moving aircraft out of the way of the unidentified aircraft (believed to be United 175) as it moved southwest and then turned northeast toward New York City.
    The controller responded, seconds later: "Somebody call Cleveland?"This was followed by a second radio transmission, with sounds of screaming. The Cleveland Center controllers began to try to identify the possible source of the transmissions, and noticed that United 93 had descended some 700 feet. The controller attempted again to raise United 93 several times, with no response. At 9:30, the controller began to poll the other flights on his frequency to determine if they had heard the screaming; several said they had.
hojoon@Hojoons-MacBook-Pro docsearch_wk5 % 
```

-i (ignore-case): Ignores case distinctions in patterns and input data. This searches for word flights that is in the file and show output.
```
grep -i chapter ./technical/911report/
```
```
grep: ./technical/911report/: Is a directory
```
-i (ignore-case): Ignores case distinctions in patterns and input data. This is used in directory not file so it shows that given is directory.

```
grep -w flights ./technical/911report/chapter-1.txt
```
```
The 19 men were aboard four transcontinental flights.
    The hijackers attacked sometime between 8:42 and 8:46. They used knives (as reported by two passengers and a flight attendant), Mace (reported by one passenger), and the threat of a bomb (reported by the same passenger). They stabbed members of the flight crew (reported by a flight attendant and one passenger). Both pilots had been killed (reported by one flight attendant). The eyewitness accounts came from calls made from the rear of the plane, from passengers originally seated further forward in the cabin, a sign that passengers and perhaps crew had been moved to the back of the aircraft. Given similarities to American 11 in hijacker seating and in eyewitness reports of tactics and weapons, as well as the contact between the presumed team leaders, Atta and Shehhi, we believe the tactics were similar on both flights.
    American 77 pushed back from its gate at 8:09 and took off at 8:20. At 8:46, the flight reached its assigned cruising altitude of 35,000 feet. Cabin service would have begun. At 8:51, American 77 transmitted its last routine radio communication. The hijacking began between 8:51 and 8:54. As on American 11 and United 175, the hijackers used knives (reported by one passenger) and moved all the passengers (and possibly crew) to the rear of the aircraft (reported by one flight attendant and one passenger). Unlike the earlier flights, the Flight 77 hijackers were reported by a passenger to have box cutters. Finally, a passenger reported that an announcement had been made by the "pilot" that the plane had been hijacked. Neither of the firsthand accounts mentioned any stabbings or the threat or use of either a bomb or Mace, though both witnesses began the flight in the first-class cabin.
    At 9:00, American Airlines Executive Vice President Gerard Arpey learned that communications had been lost with American 77. This was now the second American aircraft in trouble. He ordered all American Airlines flights in the Northeast that had not taken off to remain on the ground. Shortly before 9:10, suspecting that American 77 had been hijacked, American headquarters concluded that the second aircraft to hit the World Trade Center might have been Flight 77. After learning that United Airlines was missing a plane, American Airlines headquarters extended the ground stop nationwide.
    The hijackers had planned to take flights scheduled to depart at 7:45 (American 11), 8:00 (United 175 and United 93), and 8:10 (American 77). Three of the flights had actually taken off within 10 to 15 minutes of their planned departure times. United 93 would ordinarily have taken off about 15 minutes after pulling away from the gate. When it left the ground at 8:42, the flight was running more than 25 minutes late.
    The airlines bore responsibility, too. They were facing an escalating number of conflicting and, for the most part, erroneous reports about other flights, as well as a continuing lack of vital information from the FAA about the hijacked flights. We found no evidence, however, that American Airlines sent any cockpit warnings to its aircraft on 9/11. United's first decisive action to notify its airborne aircraft to take defensive action did not come until 9:19, when a United flight dispatcher, Ed Ballinger, took the initiative to begin transmitting warnings to his 16 transcontinental flights: "Beware any cockpit intrusion- Two a/c [aircraft] hit World Trade Center." One of the flights that received the warning was United 93. Because Ballinger was still responsible for his other flights as well as Flight 175, his warning message was not transmitted to Flight 93 until 9:23.
    The terrorists who hijacked three other commercial flights on 9/11 operated in five-man teams. They initiated their cockpit takeover within 30 minutes of takeoff. On Flight 93, however, the takeover took place 46 minutes after takeoff and there were only four hijackers. The operative likely intended to round out the team for this flight, Mohamed al Kahtani, had been refused entry by a suspicious immigration inspector at Florida's Orlando International Airport in August.
    At least two callers from the flight reported that the hijackers knew that passengers were making calls but did not seem to care. It is quite possible Jarrah knew of the success of the assault on the World Trade Center. He could have learned of this from messages being sent by United Airlines to the cockpits of its transcontinental flights, including Flight 93, warning of cockpit intrusion and telling of the New York attacks. But even without them, he would certainly have understood that the attacks on the World Trade Center would already have unfolded, given Flight 93's tardy departure from Newark. If Jarrah did know that the passengers were making calls, it might not have occurred to him that they were certain to learn what had happened in New York, thereby defeating his attempts at deception.
    Passengers on three flights reported the hijackers' claim of having a bomb. The FBI told us they found no trace of explosives at the crash sites. One of the passengers who mentioned a bomb expressed his belief that it was not real. Lacking any evidence that the hijackers attempted to smuggle such illegal items past the security screening checkpoints, we believe the bombs were probably fake.
    Another commercial aircraft in the vicinity then radioed in with "reports over the radio of a commuter plane hitting the World Trade Center." The controller spent the next several minutes handing off the other flights on his scope to other controllers and moving aircraft out of the way of the unidentified aircraft (believed to be United 175) as it moved southwest and then turned northeast toward New York City.
    The controller responded, seconds later: "Somebody call Cleveland?"This was followed by a second radio transmission, with sounds of screaming. The Cleveland Center controllers began to try to identify the possible source of the transmissions, and noticed that United 93 had descended some 700 feet. The controller attempted again to raise United 93 several times, with no response. At 9:30, the controller began to poll the other flights on his frequency to determine if they had heard the screaming; several said they had.
```

-w (word-regexp): Finds the exact matching word from the input file or string.

```
grep -w chapter ./technical/911report/
```

```
grep: ./technical/911report/: Is a directory
```

-w (word-regexp): Finds the exact matching word from the input file or string. Returns that it is directory.

```
grep -v have ./technical/911report/chapter-1.txt
```
```
For those heading to an airport, weather conditions could not have been better for a safe and pleasant journey. Among the travelers were Mohamed Atta and Abdul Aziz al Omari, who arrived at the airport in Portland, Maine.
    In passing through these checkpoints, each of the hijackers would have been screened by a walk-through metal detector calibrated to detect items with at least the metal content of a .22-caliber handgun. Anyone who might have set off that detector would have been screened with a hand wand-a procedure requiring the screener to identify the metal item or items that caused the alarm. In addition, an X-ray machine would have screened the hijackers' carry-on belongings. The screening was in place to identify and confiscate weapons and other items prohibited from being carried onto a commercial flight.
    Hani Hanjour, Khalid al Mihdhar, and Majed Moqed were flagged by CAPPS. The Hazmi brothers were also selected for extra scrutiny by the airline's customer service representative at the check-in counter. He did so because one of the brothers did not have photo identification nor could he understand English, and because the agent found both of the passengers to be suspicious. The only consequence of their selection was that their checked bags were held off the plane until it was confirmed that they had boarded the aircraft.
    When the local civil aviation security office of the Federal Aviation Administration (FAA) later investigated these security screening operations, the screeners recalled nothing out of the ordinary. They could not recall that any of the passengers they screened were CAPPS selectees. We asked a screening expert to review the videotape of the hand-wanding, and he found the quality of the screener's work to have been "marginal at best." The screener should have "resolved" what set off the alarm; and in the case of both Moqed and Hazmi, it was clear that he did not.
    The four men passed through the security checkpoint, owned by United Airlines and operated under contract by Argenbright Security. Like the checkpoints in Boston, it lacked closed-circuit television surveillance so there is no documentary evidence to indicate when the hijackers passed through the checkpoint, what alarms may have been triggered, or what security procedures were administered. The FAA interviewed the screeners later; none recalled anything unusual or suspicious.
    They were planning to hijack these planes and turn them into large guided missiles, loaded with up to 11,400 gallons of jet fuel. By 8:00 A.M. on the morning of Tuesday, September 11,2001, they had defeated all the security layers that America's civil aviation security system then had in place to prevent a hijacking. The Hijacking of American 11 American Airlines Flight 11 provided nonstop service from Boston to Los Angeles. On September 11, Captain John Ogonowski and First Officer Thomas McGuinness piloted the Boeing 767. It carried its full capacity of nine flight attendants. Eighty-one passengers boarded the flight with them (including the five terrorists).22 The plane took off at 7:59. Just before 8:14, it had climbed to 26,000 feet, not quite its initial assigned cruising altitude of 29,000 feet. All communications and flight profile data were normal. About this time the "Fasten Seatbelt" sign would usually have been turned off and the flight attendants would have begun preparing for cabin service.
    Reports from two flight attendants in the coach cabin, Betty Ong and Madeline "Amy" Sweeney, tell us most of what we know about how the hijacking happened. As it began, some of the hijackers-most likely Wail al Shehri and Waleed al Shehri, who were seated in row 2 in first class-stabbed the two unarmed flight attendants who would have been preparing for cabin service.
    We do not know exactly how the hijackers gained access to the cockpit; FAA rules required that the doors remain closed and locked during flight. Ong speculated that they had "jammed their way" in. Perhaps the terrorists stabbed the flight attendants to get a cockpit key, to force one of them to open the cockpit door, or to lure the captain or first officer out of the cockpit. Or the flight attendants may just have been in their way.
    At the same time or shortly thereafter, Atta-the only terrorist on board trained to fly a jet-would have moved to the cockpit from his business-class seat, possibly accompanied by Omari. As this was happening, passenger Daniel Lewin, who was seated in the row just behind Atta and Omari, was stabbed by one of the hijackers-probably Satam al Suqami, who was seated directly behind Lewin. Lewin had served four years as an officer in the Israeli military. He may have made an attempt to stop the hijackers in front of him, not realizing that another was sitting behind him.
    At 8:41, in American's operations center, a colleague told Marquis that the air traffic controllers declared Flight 11 a hijacking and "think he's [American 11] headed toward Kennedy [airport in New York City]. They're moving everybody out of the way. They seem to have him on a primary radar. They seem to think that he is descending."
    United 175 pushed back from its gate at 7:58 and departed Logan Airport at 8:14. By 8:33, it had reached its assigned cruising altitude of 31,000 feet. The flight attendants would have begun their cabin service.
    The flight had taken off just as American 11 was being hijacked, and at 8:42 the United 175 flight crew completed their report on a "suspicious transmission" overheard from another plane (which turned out to have been Flight 11) just after takeoff. This was United 175's last communication with the ground.
    At 8:52, in Easton, Connecticut, a man named Lee Hanson received a phone call from his son Peter, a passenger on United 175. His son told him: "I think they've taken over the cockpit-An attendant has been stabbed- and someone else up front may have been killed. The plane is making strange moves. Call United Airlines-Tell them it's Flight 175, Boston to LA." Lee Hanson then called the Easton Police Department and relayed what he had heard.
    At 9:00, Lee Hanson received a second call from his son Peter: It's getting bad, Dad-A stewardess was stabbed-They seem to have knives and Mace-They said they have a bomb-It's getting very bad on the plane-Passengers are throwing up and getting sick-The plane is making jerky movements-I don't think the pilot is flying the plane-I think we are going down-I think they intend to go to Chicago or someplace and fly into a building-Don't worry, Dad- If it happens, it'll be very fast-My God, my God.
    American 77 pushed back from its gate at 8:09 and took off at 8:20. At 8:46, the flight reached its assigned cruising altitude of 35,000 feet. Cabin service would have begun. At 8:51, American 77 transmitted its last routine radio communication. The hijacking began between 8:51 and 8:54. As on American 11 and United 175, the hijackers used knives (reported by one passenger) and moved all the passengers (and possibly crew) to the rear of the aircraft (reported by one flight attendant and one passenger). Unlike the earlier flights, the Flight 77 hijackers were reported by a passenger to have box cutters. Finally, a passenger reported that an announcement had been made by the "pilot" that the plane had been hijacked. Neither of the firsthand accounts mentioned any stabbings or the threat or use of either a bomb or Mace, though both witnesses began the flight in the first-class cabin.
    At 9:00, American Airlines Executive Vice President Gerard Arpey learned that communications had been lost with American 77. This was now the second American aircraft in trouble. He ordered all American Airlines flights in the Northeast that had not taken off to remain on the ground. Shortly before 9:10, suspecting that American 77 had been hijacked, American headquarters concluded that the second aircraft to hit the World Trade Center might have been Flight 77. After learning that United Airlines was missing a plane, American Airlines headquarters extended the ground stop nationwide.
    At 9:32, controllers at the Dulles Terminal Radar Approach Control "observed a primary radar target tracking eastbound at a high rate of speed." This was later determined to have been Flight 77.
    The hijackers had planned to take flights scheduled to depart at 7:45 (American 11), 8:00 (United 175 and United 93), and 8:10 (American 77). Three of the flights had actually taken off within 10 to 15 minutes of their planned departure times. United 93 would ordinarily have taken off about 15 minutes after pulling away from the gate. When it left the ground at 8:42, the flight was running more than 25 minutes late.
    At the same time, Boston Center realized that a message transmitted just before 8:25 by the hijacker pilot of American 11 included the phrase, "We have some planes."
    No one at the FAA or the airlines that day had ever dealt with multiple hijackings. Such a plot had not been carried out anywhere in the world in more than 30 years, and never in the United States. As news of the hijackings filtered through the FAA and the airlines, it does not seem to have occurred to their leadership that they needed to alert other aircraft in the air that they too might be at risk.
    Because several passengers on United 93 described three hijackers on the plane, not four, some have wondered whether one of the hijackers had been able to use the cockpit jump seat from the outset of the flight. FAA rules allow use of this seat by documented and approved individuals, usually air carrier or FAA personnel. We have found no evidence indicating that one of the hijackers, or anyone else, sat there on this flight. All the hijackers had assigned seats in first class, and they seem to have used them. We believe it is more likely that Jarrah, the crucial pilot-trained member of their team, remained seated and inconspicuous until after the cockpit was seized; and once inside, he would not have been visible to the passengers.
    At 9:32, a hijacker, probably Jarrah, made or attempted to make the following announcement to the passengers of Flight 93:"Ladies and Gentlemen: Here the captain, please sit down keep remaining sitting. We have a bomb on board. So, sit." The flight data recorder (also recovered) indicates that Jarrah then instructed the plane's autopilot to turn the aircraft around and head east.
    While it apparently was not heard by the passengers, this announcement, like those on Flight 11 and Flight 77, was intended to deceive them. Jarrah, like Atta earlier, may have inadvertently broadcast the message because he did not know how to operate the radio and the intercom. To our knowledge none of them had ever flown an actual airliner before.
    At least two callers from the flight reported that the hijackers knew that passengers were making calls but did not seem to care. It is quite possible Jarrah knew of the success of the assault on the World Trade Center. He could have learned of this from messages being sent by United Airlines to the cockpits of its transcontinental flights, including Flight 93, warning of cockpit intrusion and telling of the New York attacks. But even without them, he would certainly have understood that the attacks on the World Trade Center would already have unfolded, given Flight 93's tardy departure from Newark. If Jarrah did know that the passengers were making calls, it might not have occurred to him that they were certain to learn what had happened in New York, thereby defeating his attempts at deception.
    At least ten passengers and two crew members shared vital information with family, friends, colleagues, or others on the ground. All understood the plane had been hijacked. They said the hijackers wielded knives and claimed to have a bomb. The hijackers were wearing red bandanas, and they forced the passengers to the back of the aircraft.
    One of the callers from United 93 also reported that he thought the hijackers might possess a gun. But none of the other callers reported the presence of a firearm. One recipient of a call from the aircraft recounted specifically asking her caller whether the hijackers had guns. The passenger replied that he did not see one. No evidence of firearms or of their identifiable remains was found at the aircraft's crash site, and the cockpit voice recorder gives no indication of a gun being fired or mentioned at any time. We believe that if the hijackers had possessed a gun, they would have used it in the flight's last minutes as the passengers fought back.
    The passengers continued their assault and at 10:02:23, a hijacker said, "Pull it down! Pull it down!"The hijackers remained at the controls but must have judged that the passengers were only seconds from overcoming them. The airplane headed down; the control wheel was turned hard to the right. The airplane rolled onto its back, and one of the hijackers began shouting "Allah is the greatest. Allah is the greatest." With the sounds of the passenger counterattack continuing, the aircraft plowed into an empty field in Shanksville, Pennsylvania, at 580 miles per hour, about 20 minutes' flying time from Washington, D.C.
    Prior to 9/11, it was understood that an order to shoot down a commercial aircraft would have to be issued by the National Command Authority (a phrase used to describe the president and secretary of defense). Exercise planners also assumed that the aircraft would originate from outside the United States, allowing time to identify the target and scramble interceptors. The threat of terrorists hijacking commercial airliners within the United States-and using them as guided missiles-was not recognized by NORAD before 9/11. Notwithstanding the identification of these emerging threats, by 9/11 there were only seven alert sites left in the United States, each with two fighter aircraft on alert. This led some NORAD commanders to worry that NORAD was not postured adequately to protect the United States.
    The NMCC would keep the FAA hijack coordinator up to date and help the FAA centers coordinate directly with the military. NORAD would receive tracking information for the hijacked aircraft either from joint use radar or from the relevant FAA air traffic control facility. Every attempt would be made to have the hijacked aircraft squawk 7500 to help NORAD track it.
    At 8:24:38, the following transmission came from American 11: American 11: We have some planes. Just stay quiet, and you'll be okay. We are returning to the airport.
    The controller only heard something unintelligible; he did not hear the specific words "we have some planes." The next transmission came seconds later: American 11: Nobody move. Everything will be okay. If you try to make any moves, you'll endanger yourself and the airplane. Just stay quiet.
    FAA: Hi. Boston Center TMU [Traffic Management Unit], we have a problem here. We have a hijacked aircraft headed towards New York, and we need you guys to, we need someone to scramble some F-16s or something up there, help us out.
    Manager, New York Center: Okay. This is New York Center. We're watching the airplane. I also had conversation with American Airlines, and they've told us that they believe that one of their stewardesses was stabbed and that there are people in the cockpit that have control of the aircraft, and that's all the information they have right now.
    At 8:51, the controller noticed the transponder change from United 175 and tried to contact the aircraft. There was no response. Beginning at 8:52, the controller made repeated attempts to reach the crew of United 175. Still no response. The controller checked his radio equipment and contacted another controller at 8:53, saying that "we may have a hijack" and that he could not find the aircraft.
    At about 8:55, the controller in charge notified a New York Center manager that she believed United 175 had also been hijacked. The manager tried to notify the regional managers and was told that they were discussing a hijacked aircraft (presumably American 11) and refused to be disturbed. At 8:58, the New York Center controller searching for United 175 told another New York controller "we might have a hijack over here, two of them."
    Manager, New York Center: We have several situations going on here. It's escalating big, big time. We need to get the military involved with us. . . . We're, we're involved with something else, we have other aircraft that may have a similar situation going on here.
    Boston Center: . . . as far as the tape, Bobby seemed to think the guy said that "we have planes." Now, I don't know if it was because it was the accent, or if there's more than one, but I'm gonna, I'm gonna reconfirm that for you, and I'll get back to you real quick. Okay? New England Region: Appreciate it.
    Unidentified Female Voice: They have what?
    Boston Center immediately advised the New England Region that it was going to stop all departures at airports under its control. At 9:05, Boston Center confirmed for both the FAA Command Center and the New England Region that the hijackers aboard American 11 said "we have planes." At the same time, New York Center declared "ATC zero"-meaning that aircraft were not permitted to depart from, arrive at, or travel through New York Center's airspace until further notice.
    Within minutes of the second impact, Boston Center instructed its controllers to inform all aircraft in its airspace of the events in New York and to advise aircraft to heighten cockpit security. Boston Center asked the Herndon Command Center to issue a similar cockpit security alert nationwide. We have found no evidence to suggest that the Command Center acted on this request or issued any type of cockpit security alert.
    By 9:25, FAA's Herndon Command Center and FAA headquarters knew two aircraft had crashed into the World Trade Center. They knew American 77 was lost. At least some FAA officials in Boston Center and the New England Region knew that a hijacker on board American 11 had said "we have some planes." Concerns over the safety of other aircraft began to mount. A manager at the Herndon Command Center asked FAA headquarters if they wanted to order a "nationwide ground stop." While this was being discussed by executives at FAA headquarters, the Command Center ordered one at 9:25.
    FAA: That was another-it was evidently another aircraft that hit the tower. That's the latest report we have.
    The mention of a "third aircraft" was not a reference to American 77. There was confusion at that moment in the FAA. Two planes had struck the World Trade Center, and Boston Center had heard from FAA headquarters in Washington that American 11 was still airborne. We have been unable to identify the source of this mistaken FAA information.
    At the suggestion of the Boston Center's military liaison, NEADS contacted the FAA's Washington Center to ask about American 11. In the course of the conversation, a Washington Center manager informed NEADS:"We're looking- we also lost American 77." The time was 9:34. This was the first notice to the military that American 77 was missing, and it had come by chance. If NEADS had not placed that call, the NEADS air defenders would have received no information whatsoever that the flight was even missing, although the FAA had been searching for it. No one at FAA headquarters ever asked for military assistance with American 77.
    Right after the Pentagon was hit, NEADS learned of another possible hijacked aircraft. It was an aircraft that in fact had not been hijacked at all. After the second World Trade Center crash, Boston Center managers recognized that both aircraft were transcontinental 767 jetliners that had departed Logan Airport. Remembering the "we have some planes" remark, Boston Center guessed that Delta 1989 might also be hijacked. Boston Center called NEADS at 9:41 and identified Delta 1989, a 767 jet that had left Logan Airport for Las Vegas, as a possible hijack. NEADS warned the FAA's Cleveland Center to watch Delta 1989. The Command Center and FAA headquarters watched it too. During the course of the morning, there were multiple erroneous reports of hijacked aircraft. The report of American 11 heading south was the first; Delta 1989 was the second.
    At 9:32, a third radio transmission came over the frequency:"Keep remaining sitting. We have a bomb on board." The controller understood, but chose to respond: "Calling Cleveland Center, you're unreadable. Say again, slowly." He notified his supervisor, who passed the notice up the chain of command. By 9:34, word of the hijacking had reached FAA headquarters.
    FAA headquarters had by this time established an open line of communication with the Command Center at Herndon and instructed it to poll all its centers about suspect aircraft. The Command Center executed the request and, a minute later, Cleveland Center reported that "United 93 may have a bomb on board." At 9:34, the Command Center relayed the information concerning United 93 to FAA headquarters. At approximately 9:36, Cleveland advised the Command Center that it was still tracking United 93 and specifically inquired whether someone had requested the military to launch fighter aircraft to intercept the aircraft. Cleveland even told the Command Center it was prepared to contact a nearby military base to make the request. The Command Center told Cleveland that FAA personnel well above them in the chain of command had to make the decision to seek military assistance and were working on the issue.
    Then, at 9:39, a fourth radio transmission was heard from United 93: Ziad Jarrah: Uh, this is the captain. Would like you all to remain seated. There is a bomb on board and are going back to the airport, and to have our demands [unintelligible]. Please remain quiet.
    The controller responded: "United 93, understand you have a bomb on board. Go ahead." The flight did not respond.
    Command Center: Uh, that's a decision somebody's gonna have to make probably in the next ten minutes.
    NEADS: United nine three, have you got information on that yet? FAA: Yeah, he's down.
    NEADS: When did he land? 'Cause we have got confirmation- FAA: He did not land.
    Thus the military did not have 14 minutes to respond to American 77, as testimony to the Commission in May 2003 suggested. It had at most one or two minutes to react to the unidentified plane approaching Washington, and the fighters were in the wrong place to be able to help. They had been responding to a report about an aircraft that did not exist.
    Nor did the military have 47 minutes to respond to United 93, as would be implied by the account that it received notice of the flight's hijacking at 9:16. By the time the military learned about the flight, it had crashed. We now turn to the role of national leadership in the events that morning.
    In Sarasota, Florida, the presidential motorcade was arriving at the Emma E. Booker Elementary School, where President Bush was to read to a class and talk about education. White House Chief of Staff Andrew Card told us he was standing with the President outside the classroom when Senior Advisor to the President Karl Rove first informed them that a small, twin-engine plane had crashed into the World Trade Center. The President's reaction was that the incident must have been caused by pilot error.
    The President and the Vice President The President was seated in a classroom when, at 9:05, Andrew Card whispered to him: "A second plane hit the second tower. America is under attack." The President told us his instinct was to project calm, not to have the country see an excited reaction at a moment of crisis. The press was standing behind the children; he saw their phones and pagers start to ring. The President felt he should project strength and calm until he could better understand what was happening.
    The President's motorcade departed at 9:35, and arrived at the airport between 9:42 and 9:45. During the ride the President learned about the attack on the Pentagon. He boarded the aircraft, asked the Secret Service about the safety of his family, and called the Vice President. According to notes of the call, at about 9:45 the President told the Vice President:"Sounds like we have a minor war going on here, I heard about the Pentagon. We're at war . . . somebody's going to pay."
    The Vice President remembered placing a call to the President just after entering the shelter conference room. There is conflicting evidence about when the Vice President arrived in the shelter conference room. We have concluded, from the available evidence, that the Vice President arrived in the room shortly before 10:00, perhaps at 9:58. The Vice President recalled being told, just after his arrival, that the Air Force was trying to establish a combat air patrol over Washington.
    We believe this call would have taken place sometime before 10:10 to 10:15.
    At 10:02, the communicators in the shelter began receiving reports from the Secret Service of an inbound aircraft-presumably hijacked-heading toward Washington. That aircraft was United 93. The Secret Service was getting this information directly from the FAA. The FAA may have been tracking the progress of United 93 on a display that showed its projected path to Washington, not its actual radar return. Thus, the Secret Service was relying on projections and was not aware the plane was already down in Pennsylvania.
    SecDef: So we've got a couple of aircraft up there that have those instructions at this present time?
    SecDef: We can't confirm that. We're told that one aircraft is down but we do not have a pilot report that did it.
    NORAD officials have maintained consistently that had the passengers not caused United 93 to crash, the military would have prevented it from reaching Washington, D.C. That conclusion is based on a version of events that we now know is incorrect. The Langley fighters were not scrambled in response to United 93; NORAD did not have 47 minutes to intercept the flight; NORAD did not even know the plane was hijacked until after it had crashed. It is appropriate, therefore, to reconsider whether United 93 would have been intercepted.
    Had it not crashed in Pennsylvania at 10:03, we estimate that United 93 could not have reached Washington any earlier than 10:13, and probably would have arrived before 10:23. There was only one set of fighters circling Washington during that time frame-the Langley F-16s. They were armed and under NORAD's control. After NEADS learned of the hijacking at 10:07, NORAD would have had from 6 to 16 minutes to locate the flight, receive authorization to shoot it down, and communicate the order to the pilots, who (in the same span) would have had to authenticate the order, intercept the flight, and execute the order.
    At that point in time, the Langley pilots did not know the threat they were facing, did not know where United 93 was located, and did not have shootdown authorization.
    Second, NEADS did not have accurate information on the location of United 93. Presumably FAA would have provided such information, but we do not know how long that would have taken, nor how long it would have taken NEADS to locate the target.
    Third, NEADS needed orders to pass to the pilots. At 10:10, the pilots over Washington were emphatically told, "negative clearance to shoot." Shootdown authority was first communicated to NEADS at 10:31. It is possible that NORAD commanders would have ordered a shootdown in the absence of the authorization communicated by the Vice President, but given the gravity of the decision to shoot down a commercial airliner, and NORAD's caution that a mistake not be made, we view this possibility as unlikely.
    NORAD officials have maintained that they would have intercepted and shot down United 93. We are not so sure. We are sure that the nation owes a debt to the passengers of United 93. Their actions saved the lives of countless others, and may have saved either the Capitol or the White House from destruction.
```
-v (invert-match): Selects the non-matching lines of the provided input pattern.

```
grep -v chapter ./technical/911report/
```
```
grep: ./technical/911report/: Is a directory
```
-v (invert-match): Selects the non-matching lines of the provided input pattern​. Returns that it is directory.

```
grep -n flights ./technical/911report/chapter-1.txt
```
```
60:    The 19 men were aboard four transcontinental flights.
104:    The hijackers attacked sometime between 8:42 and 8:46. They used knives (as reported by two passengers and a flight attendant), Mace (reported by one passenger), and the threat of a bomb (reported by the same passenger). They stabbed members of the flight crew (reported by a flight attendant and one passenger). Both pilots had been killed (reported by one flight attendant). The eyewitness accounts came from calls made from the rear of the plane, from passengers originally seated further forward in the cabin, a sign that passengers and perhaps crew had been moved to the back of the aircraft. Given similarities to American 11 in hijacker seating and in eyewitness reports of tactics and weapons, as well as the contact between the presumed team leaders, Atta and Shehhi, we believe the tactics were similar on both flights.
126:    American 77 pushed back from its gate at 8:09 and took off at 8:20. At 8:46, the flight reached its assigned cruising altitude of 35,000 feet. Cabin service would have begun. At 8:51, American 77 transmitted its last routine radio communication. The hijacking began between 8:51 and 8:54. As on American 11 and United 175, the hijackers used knives (reported by one passenger) and moved all the passengers (and possibly crew) to the rear of the aircraft (reported by one flight attendant and one passenger). Unlike the earlier flights, the Flight 77 hijackers were reported by a passenger to have box cutters. Finally, a passenger reported that an announcement had been made by the "pilot" that the plane had been hijacked. Neither of the firsthand accounts mentioned any stabbings or the threat or use of either a bomb or Mace, though both witnesses began the flight in the first-class cabin.
130:    At 9:00, American Airlines Executive Vice President Gerard Arpey learned that communications had been lost with American 77. This was now the second American aircraft in trouble. He ordered all American Airlines flights in the Northeast that had not taken off to remain on the ground. Shortly before 9:10, suspecting that American 77 had been hijacked, American headquarters concluded that the second aircraft to hit the World Trade Center might have been Flight 77. After learning that United Airlines was missing a plane, American Airlines headquarters extended the ground stop nationwide.
150:    The hijackers had planned to take flights scheduled to depart at 7:45 (American 11), 8:00 (United 175 and United 93), and 8:10 (American 77). Three of the flights had actually taken off within 10 to 15 minutes of their planned departure times. United 93 would ordinarily have taken off about 15 minutes after pulling away from the gate. When it left the ground at 8:42, the flight was running more than 25 minutes late.
164:    The airlines bore responsibility, too. They were facing an escalating number of conflicting and, for the most part, erroneous reports about other flights, as well as a continuing lack of vital information from the FAA about the hijacked flights. We found no evidence, however, that American Airlines sent any cockpit warnings to its aircraft on 9/11. United's first decisive action to notify its airborne aircraft to take defensive action did not come until 9:19, when a United flight dispatcher, Ed Ballinger, took the initiative to begin transmitting warnings to his 16 transcontinental flights: "Beware any cockpit intrusion- Two a/c [aircraft] hit World Trade Center." One of the flights that received the warning was United 93. Because Ballinger was still responsible for his other flights as well as Flight 175, his warning message was not transmitted to Flight 93 until 9:23.
172:    The terrorists who hijacked three other commercial flights on 9/11 operated in five-man teams. They initiated their cockpit takeover within 30 minutes of takeoff. On Flight 93, however, the takeover took place 46 minutes after takeoff and there were only four hijackers. The operative likely intended to round out the team for this flight, Mohamed al Kahtani, had been refused entry by a suspicious immigration inspector at Florida's Orlando International Airport in August.
186:    At least two callers from the flight reported that the hijackers knew that passengers were making calls but did not seem to care. It is quite possible Jarrah knew of the success of the assault on the World Trade Center. He could have learned of this from messages being sent by United Airlines to the cockpits of its transcontinental flights, including Flight 93, warning of cockpit intrusion and telling of the New York attacks. But even without them, he would certainly have understood that the attacks on the World Trade Center would already have unfolded, given Flight 93's tardy departure from Newark. If Jarrah did know that the passengers were making calls, it might not have occurred to him that they were certain to learn what had happened in New York, thereby defeating his attempts at deception.
194:    Passengers on three flights reported the hijackers' claim of having a bomb. The FBI told us they found no trace of explosives at the crash sites. One of the passengers who mentioned a bomb expressed his belief that it was not real. Lacking any evidence that the hijackers attempted to smuggle such illegal items past the security screening checkpoints, we believe the bombs were probably fake.
330:    Another commercial aircraft in the vicinity then radioed in with "reports over the radio of a commuter plane hitting the World Trade Center." The controller spent the next several minutes handing off the other flights on his scope to other controllers and moving aircraft out of the way of the unidentified aircraft (believed to be United 175) as it moved southwest and then turned northeast toward New York City.
458:    The controller responded, seconds later: "Somebody call Cleveland?"This was followed by a second radio transmission, with sounds of screaming. The Cleveland Center controllers began to try to identify the possible source of the transmissions, and noticed that United 93 had descended some 700 feet. The controller attempted again to raise United 93 several times, with no response. At 9:30, the controller began to poll the other flights on his frequency to determine if they had heard the screaming; several said they had.
```
-n (line-number): Prefix each line of the matching output with the line number in the input file.

```
grep -n chapter ./technical/911report/  
```
```
grep: ./technical/911report/: Is a directory
```

-n (line-number): Prefix each line of the matching output with the line number in the input file.  Returns that it is a directory.

Works Cited
https://www.freecodecamp.org/news/grep-command-in-linux-usage-options-and-syntax-examples/















