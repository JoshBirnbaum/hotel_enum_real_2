# hotel_enum_real_2
<HTML>
<HEAD>
</HEAD>
<BODY BGCOLOR='white' TEXT='black'
LINK='blue' VLINK='blue'
ALINK='green'>
<H1>
</H1>
<H2></H2>
<H2>Table Of Contents</H2>
<LI><A href="#REQUIREMENTS">Requirements</A href="#REQUIREMENTS"></LI>
<LI><A href="#STIMULI">Stimuli</A href="#STIMULI"></LI>
<LI><A href="#OUTPUTS">Outputs</A href="#OUTPUTS"></LI>
<LI><A href="#INTERFACES">Interfaces</A href="#INTERFACES"></LI>
<LI><A href="#NAMEDRESPONSES">Named Responses</A href="#NAMEDRESPONSES"></LI>
<LI><A href="#PREDICATES">Predicates</A href="#PREDICATES"></LI>
<LI><A href="#ENUMERATION">Sequence Enumeration</A href="#ENUMERATION"></LI>
<UL>
<LI><A href="#LENGTH1">Length 1</A></LI>
<LI><A href="#LENGTH2">Length 2</A></LI>
<LI><A href="#LENGTH3">Length 3</A></LI>
<LI><A href="#LENGTH4">Length 4</A></LI>
<LI><A href="#LENGTH5">Length 5</A></LI>
<LI><A href="#LENGTH6">Length 6</A></LI>
<LI><A href="#LENGTH7">Length 7</A></LI>
</UL>
<LI><A href="#VARIABLES">State Variables</A></LI>
<LI><A href="#CSA">Canonical Sequence Analysis</A></LI>
<LI><A href="#STATEBOX">State Box Specification</A></LI>
</UL>
<H1 id="REQUIREMENTS">Requirements</H1>
<UL>
<LI id="REQ1"><b>1:</b> There are three different screens, a home screen, a create reservation screen, and a view reservation screen.</LI>
<LI id="REQ2"><b>2:</b> Only one screen can be up at a time.</LI>
<LI id="REQ3"><b>3:</b> The home screen has a list of current reservations and a button to make a new reservation.</LI>
<LI id="REQ4"><b>4:</b> The view reservation screen comes up when the user clicks on a specific reservation on the home screen. It displays the reservation’s info.</LI>
<LI id="REQ5"><b>5:</b> The create reservation screen comes up when the user clicks on the new reservation button on the home screen. It has 5 inputs to be filled out: Guest name, phone number, room type, arrival date, and departure date. The screen also has a create reservation button.</LI>
<LI id="REQ6"><b>6:</b> All 5 input fields must be filled out to make a new reservation. If not and the button is clicked than an error message pops up and the user must fill out the inputs.</LI>
<LI id="REQ7"><b>7:</b> If all 5 input fields are filled and the user hits the create reservation button than the user is returned to the home screen where the new reservation appears in the list of current reservations.</LI>
<LI id="REQD1"><b>D1:</b> When an input field is correctly filled out in the create new reservation page there is no observable response.</LI>
<LI id="REQD2"><b>D2:</b> You can only have one page open at a time, hence trying to preform an action on a page you do not have open is illegal</LI>
<LI id="REQD3"><b>D3:</b> You can only have one reservation open at a time.</LI>
</UL>
<H1 id="INTERFACES">Interfaces</H1>
<UL>
<LI id="INTERFACECreateReservationPage"><b>CreateReservationPage</b></LI>
<UL>
<LI>Description: This is the second page in the software accessed by clicking the 'create reservation' button. It has all the input fields needed to be filled out to make a new reservation.</LI>
<LI>Requirement Trace: [<A href="#REQ1" title="There are three different screens, a home screen, a create reservation screen, and a view reservation screen.">1</A>, <A href="#REQ5" title="The create reservation screen comes up when the user clicks on the new reservation button on the home screen. It has 5 inputs to be filled out: Guest name, phone number, room type, arrival date, and departure date. The screen also has a create reservation button.">5</A>]
</LI>
</UL>
<LI id="INTERFACEHomePage"><b>HomePage</b></LI>
<UL>
<LI>Description: This is the home page of the software where the user can see a list of the current reservations and either click on one to see its info or click a button to make a new reservation.</LI>
<LI>Requirement Trace: [<A href="#REQ1" title="There are three different screens, a home screen, a create reservation screen, and a view reservation screen.">1</A>, <A href="#REQ3" title="The home screen has a list of current reservations and a button to make a new reservation.">3</A>]
</LI>
</UL>
</UL>
<H1 id="STIMULI">Stimuli</H1>
<UL>
<LI id="STIMgi"><b>gi</b></LI>
<UL>
<LI>Long Name: Good Input</LI><LI>Description: This means the user entered a good input in the correct format when making a reservation.</LI>
<LI>Sources: [<A href="#INTERFACECreateReservationPage">CreateReservationPage</A>]</LI><LI>Requirement Trace: [<A href="#REQ5" title="The create reservation screen comes up when the user clicks on the new reservation button on the home screen. It has 5 inputs to be filled out: Guest name, phone number, room type, arrival date, and departure date. The screen also has a create reservation button.">5</A>, <A href="#REQ6" title="All 5 input fields must be filled out to make a new reservation. If not and the button is clicked than an error message pops up and the user must fill out the inputs.">6</A>]
</LI>
</UL>
<LI id="STIMi"><b>i</b></LI>
<UL>
<LI>Long Name: guest reservation information</LI><LI>Description: The user can click on a guest/room on the list of reservations on the home page to see that reservations information</LI>
<LI>Sources: [<A href="#INTERFACEHomePage">HomePage</A>]</LI><LI>Requirement Trace: [<A href="#REQ4" title="The view reservation screen comes up when the user clicks on a specific reservation on the home screen. It displays the reservation’s info.">4</A>]
</LI>
</UL>
<LI id="STIMr"><b>r</b></LI>
<UL>
<LI>Long Name: Make New Reservation Button Press</LI><LI>Description: When the user presses the 'create new reservation' button on the home page</LI>
<LI>Sources: [<A href="#INTERFACEHomePage">HomePage</A>]</LI><LI>Requirement Trace: [<A href="#REQ5" title="The create reservation screen comes up when the user clicks on the new reservation button on the home screen. It has 5 inputs to be filled out: Guest name, phone number, room type, arrival date, and departure date. The screen also has a create reservation button.">5</A>]
</LI>
</UL>
<LI id="STIMsr"><b>sr</b></LI>
<UL>
<LI>Long Name: Submit New Reservation Button</LI><LI>Description: A button the user clicks when they have filled out all input fields when making a new reservation and are ready to create the reservation.</LI>
<LI>Sources: [<A href="#INTERFACECreateReservationPage">CreateReservationPage</A>]</LI><LI>Requirement Trace: [<A href="#REQ5" title="The create reservation screen comes up when the user clicks on the new reservation button on the home screen. It has 5 inputs to be filled out: Guest name, phone number, room type, arrival date, and departure date. The screen also has a create reservation button.">5</A>]
</LI>
</UL>
</UL>
<H1 id="OUTPUTS">Outputs</H1>
<UL>
<LI id="OUTPUTCreateReservation"><b>CreateReservation</b></LI>
<UL>
<LI>Long Name: Make New Reservation Button</LI><LI>Description: Button on the home page that takes the user to a new page where they can create a new hotel reservation.</LI>
<LI>Destinations: [<A href="#INTERFACEHomePage">HomePage</A>]</LI><LI>Requirement Trace: [<A href="#REQ5" title="The create reservation screen comes up when the user clicks on the new reservation button on the home screen. It has 5 inputs to be filled out: Guest name, phone number, room type, arrival date, and departure date. The screen also has a create reservation button.">5</A>]
</LI>
</UL>
<LI id="OUTPUTNewReservation"><b>NewReservation</b></LI>
<UL>
<LI>Long Name: Submit The New Reservation Button</LI><LI>Description: When the user successfully creates a reservation and hits the 'make reservation' button on the Create Reservation Page, The user is taken back to the home page and the new reservation appears on the list</LI>
<LI>Destinations: [<A href="#INTERFACECreateReservationPage">CreateReservationPage</A>]</LI><LI>Requirement Trace: [<A href="#REQ5" title="The create reservation screen comes up when the user clicks on the new reservation button on the home screen. It has 5 inputs to be filled out: Guest name, phone number, room type, arrival date, and departure date. The screen also has a create reservation button.">5</A>, <A href="#REQ7" title="If all 5 input fields are filled and the user hits the create reservation button than the user is returned to the home screen where the new reservation appears in the list of current reservations.">7</A>]
</LI>
</UL>
<LI id="OUTPUTReservationError"><b>ReservationError</b></LI>
<UL>
<LI>Long Name: Create Reservation Error</LI><LI>Description: Error message when the page for making a new reservation is not completed correctly</LI>
<LI>Destinations: [<A href="#INTERFACECreateReservationPage">CreateReservationPage</A>]</LI><LI>Requirement Trace: [<A href="#REQ6" title="All 5 input fields must be filled out to make a new reservation. If not and the button is clicked than an error message pops up and the user must fill out the inputs.">6</A>]
</LI>
</UL>
<LI id="OUTPUTReservationInfo"><b>ReservationInfo</b></LI>
<UL>
<LI>Long Name: Reservation Info Pop up</LI><LI>Description: When the user clicks on a reservation on the home page the software displays the information for that reservation.</LI>
<LI>Destinations: [<A href="#INTERFACEHomePage">HomePage</A>]</LI><LI>Requirement Trace: [<A href="#REQ4" title="The view reservation screen comes up when the user clicks on a specific reservation on the home screen. It displays the reservation’s info.">4</A>]
</LI>
</UL>
</UL>
<H1 id="NAMEDRESPONSES">Named Responses</H1>
There are no named responses.
<UL>
</UL>
<H1 id="PREDICATES">Predicates</H1>
There are no named predicates.
<UL>
</UL>
<H1 id="ENUMERATION">Sequence Enumeration</H1>

<H2 id="LENGTH1">Length 1</H2>


<H3 if="&lt;lambda&gt;">Prefix: 

<A href="#<lambda>">&lt;lambda&gt;</A></H3>


<TABLE border="2">
<TR>
<TH>Stimulus</TH>
<TH>Response</TH>
<TH>Response Trace</TH>
<TH>Equivalence</TH>
<TH>Equivalence Trace</TH>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMgi" title="Good Input">gi</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQD2" title="You can only have one page open at a time, hence trying to preform an action on a page you do not have open is illegal">D2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR>
<TD>
<A href="#STIMi" title="guest reservation information">i</A></TD>
<TD>
<UL>
<LI>
<A href="#OUTPUTReservationInfo" title="Reservation Info Pop up">ReservationInfo</A>
</LI>
</UL>
</TD>
<TD>
[<A href="#REQ4" title="The view reservation screen comes up when the user clicks on a specific reservation on the home screen. It displays the reservation’s info.">4</A>]
</TD>
<TD>
<A href="#i">NONE</A>
</TD>
<TD>
[]
</TD>
</TR>
<TR>
<TD>
<A href="#STIMr" title="Make New Reservation Button Press">r</A></TD>
<TD>
<UL>
<LI>
<A href="#OUTPUTCreateReservation" title="Make New Reservation Button">CreateReservation</A>
</LI>
</UL>
</TD>
<TD>
[<A href="#REQ5" title="The create reservation screen comes up when the user clicks on the new reservation button on the home screen. It has 5 inputs to be filled out: Guest name, phone number, room type, arrival date, and departure date. The screen also has a create reservation button.">5</A>]
</TD>
<TD>
<A href="#r">NONE</A>
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMsr" title="Submit New Reservation Button">sr</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQD2" title="You can only have one page open at a time, hence trying to preform an action on a page you do not have open is illegal">D2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
</TABLE>

<H2 id="LENGTH2">Length 2</H2>


<H3 if="i">Prefix: 

<A href="#i">i</A></H3>


<TABLE border="2">
<TR>
<TH>Stimulus</TH>
<TH>Response</TH>
<TH>Response Trace</TH>
<TH>Equivalence</TH>
<TH>Equivalence Trace</TH>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMgi" title="Good Input">gi</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQD2" title="You can only have one page open at a time, hence trying to preform an action on a page you do not have open is illegal">D2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMi" title="guest reservation information">i</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQD3" title="You can only have one reservation open at a time.">D3</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMr" title="Make New Reservation Button Press">r</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQD2" title="You can only have one page open at a time, hence trying to preform an action on a page you do not have open is illegal">D2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMsr" title="Submit New Reservation Button">sr</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQD2" title="You can only have one page open at a time, hence trying to preform an action on a page you do not have open is illegal">D2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
</TABLE>

<H3 if="r">Prefix: 

<A href="#r">r</A></H3>


<TABLE border="2">
<TR>
<TH>Stimulus</TH>
<TH>Response</TH>
<TH>Response Trace</TH>
<TH>Equivalence</TH>
<TH>Equivalence Trace</TH>
</TR>
<TR>
<TD>
<A href="#STIMgi" title="Good Input">gi</A></TD>
<TD>
<UL>
</UL>
</TD>
<TD>
[<A href="#REQD1" title="When an input field is correctly filled out in the create new reservation page there is no observable response.">D1</A>]
</TD>
<TD>
<A href="#rAAAgi">NONE</A>
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMi" title="guest reservation information">i</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQ2" title="Only one screen can be up at a time.">2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMr" title="Make New Reservation Button Press">r</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQ2" title="Only one screen can be up at a time.">2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR>
<TD>
<A href="#STIMsr" title="Submit New Reservation Button">sr</A></TD>
<TD>
<UL>
<LI>
<A href="#OUTPUTReservationError" title="Create Reservation Error">ReservationError</A>
</LI>
</UL>
</TD>
<TD>
[<A href="#REQ6" title="All 5 input fields must be filled out to make a new reservation. If not and the button is clicked than an error message pops up and the user must fill out the inputs.">6</A>]
</TD>
<TD>
<A href="#rAAAsr">NONE</A>
</TD>
<TD>
[]
</TD>
</TR>
</TABLE>

<H2 id="LENGTH3">Length 3</H2>


<H3 if="rAAAgi">Prefix: 

<A href="#rAAAgi">r.gi</A></H3>


<TABLE border="2">
<TR>
<TH>Stimulus</TH>
<TH>Response</TH>
<TH>Response Trace</TH>
<TH>Equivalence</TH>
<TH>Equivalence Trace</TH>
</TR>
<TR>
<TD>
<A href="#STIMgi" title="Good Input">gi</A></TD>
<TD>
<UL>
</UL>
</TD>
<TD>
[<A href="#REQD1" title="When an input field is correctly filled out in the create new reservation page there is no observable response.">D1</A>]
</TD>
<TD>
<A href="#rAAAgiAAAgi">NONE</A>
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMi" title="guest reservation information">i</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQ2" title="Only one screen can be up at a time.">2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMr" title="Make New Reservation Button Press">r</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQ2" title="Only one screen can be up at a time.">2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR>
<TD>
<A href="#STIMsr" title="Submit New Reservation Button">sr</A></TD>
<TD>
<UL>
<LI>
<A href="#OUTPUTReservationError" title="Create Reservation Error">ReservationError</A>
</LI>
</UL>
</TD>
<TD>
[<A href="#REQ6" title="All 5 input fields must be filled out to make a new reservation. If not and the button is clicked than an error message pops up and the user must fill out the inputs.">6</A>]
</TD>
<TD>
<A href="#rAAAgiAAAsr">r.sr</A>
</TD>
<TD>
[<A href="#REQ6" title="All 5 input fields must be filled out to make a new reservation. If not and the button is clicked than an error message pops up and the user must fill out the inputs.">6</A>]
</TD>
</TR>
</TABLE>

<H3 if="rAAAsr">Prefix: 

<A href="#rAAAsr">r.sr</A></H3>


<TABLE border="2">
<TR>
<TH>Stimulus</TH>
<TH>Response</TH>
<TH>Response Trace</TH>
<TH>Equivalence</TH>
<TH>Equivalence Trace</TH>
</TR>
<TR>
<TD>
<A href="#STIMgi" title="Good Input">gi</A></TD>
<TD>
<UL>
</UL>
</TD>
<TD>
[<A href="#REQD1" title="When an input field is correctly filled out in the create new reservation page there is no observable response.">D1</A>]
</TD>
<TD>
<A href="#rAAAsrAAAgi">r.gi</A>
</TD>
<TD>
[<A href="#REQD1" title="When an input field is correctly filled out in the create new reservation page there is no observable response.">D1</A>]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMi" title="guest reservation information">i</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQ2" title="Only one screen can be up at a time.">2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMr" title="Make New Reservation Button Press">r</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQD2" title="You can only have one page open at a time, hence trying to preform an action on a page you do not have open is illegal">D2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR>
<TD>
<A href="#STIMsr" title="Submit New Reservation Button">sr</A></TD>
<TD>
<UL>
<LI>
<A href="#OUTPUTReservationError" title="Create Reservation Error">ReservationError</A>
</LI>
</UL>
</TD>
<TD>
[<A href="#REQ6" title="All 5 input fields must be filled out to make a new reservation. If not and the button is clicked than an error message pops up and the user must fill out the inputs.">6</A>]
</TD>
<TD>
<A href="#rAAAsrAAAsr">r.sr</A>
</TD>
<TD>
[<A href="#REQ6" title="All 5 input fields must be filled out to make a new reservation. If not and the button is clicked than an error message pops up and the user must fill out the inputs.">6</A>]
</TD>
</TR>
</TABLE>

<H2 id="LENGTH4">Length 4</H2>


<H3 if="rAAAgiAAAgi">Prefix: 

<A href="#rAAAgiAAAgi">r.gi.gi</A></H3>


<TABLE border="2">
<TR>
<TH>Stimulus</TH>
<TH>Response</TH>
<TH>Response Trace</TH>
<TH>Equivalence</TH>
<TH>Equivalence Trace</TH>
</TR>
<TR>
<TD>
<A href="#STIMgi" title="Good Input">gi</A></TD>
<TD>
<UL>
</UL>
</TD>
<TD>
[<A href="#REQD1" title="When an input field is correctly filled out in the create new reservation page there is no observable response.">D1</A>]
</TD>
<TD>
<A href="#rAAAgiAAAgiAAAgi">NONE</A>
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMi" title="guest reservation information">i</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQ2" title="Only one screen can be up at a time.">2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMr" title="Make New Reservation Button Press">r</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQ2" title="Only one screen can be up at a time.">2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR>
<TD>
<A href="#STIMsr" title="Submit New Reservation Button">sr</A></TD>
<TD>
<UL>
<LI>
<A href="#OUTPUTReservationError" title="Create Reservation Error">ReservationError</A>
</LI>
</UL>
</TD>
<TD>
[<A href="#REQ6" title="All 5 input fields must be filled out to make a new reservation. If not and the button is clicked than an error message pops up and the user must fill out the inputs.">6</A>]
</TD>
<TD>
<A href="#rAAAgiAAAgiAAAsr">r.sr</A>
</TD>
<TD>
[<A href="#REQ6" title="All 5 input fields must be filled out to make a new reservation. If not and the button is clicked than an error message pops up and the user must fill out the inputs.">6</A>]
</TD>
</TR>
</TABLE>

<H2 id="LENGTH5">Length 5</H2>


<H3 if="rAAAgiAAAgiAAAgi">Prefix: 

<A href="#rAAAgiAAAgiAAAgi">r.gi.gi.gi</A></H3>


<TABLE border="2">
<TR>
<TH>Stimulus</TH>
<TH>Response</TH>
<TH>Response Trace</TH>
<TH>Equivalence</TH>
<TH>Equivalence Trace</TH>
</TR>
<TR>
<TD>
<A href="#STIMgi" title="Good Input">gi</A></TD>
<TD>
<UL>
</UL>
</TD>
<TD>
[<A href="#REQD1" title="When an input field is correctly filled out in the create new reservation page there is no observable response.">D1</A>]
</TD>
<TD>
<A href="#rAAAgiAAAgiAAAgiAAAgi">NONE</A>
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMi" title="guest reservation information">i</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQ2" title="Only one screen can be up at a time.">2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMr" title="Make New Reservation Button Press">r</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQ2" title="Only one screen can be up at a time.">2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR>
<TD>
<A href="#STIMsr" title="Submit New Reservation Button">sr</A></TD>
<TD>
<UL>
<LI>
<A href="#OUTPUTReservationError" title="Create Reservation Error">ReservationError</A>
</LI>
</UL>
</TD>
<TD>
[<A href="#REQ6" title="All 5 input fields must be filled out to make a new reservation. If not and the button is clicked than an error message pops up and the user must fill out the inputs.">6</A>]
</TD>
<TD>
<A href="#rAAAgiAAAgiAAAgiAAAsr">r.sr</A>
</TD>
<TD>
[<A href="#REQ6" title="All 5 input fields must be filled out to make a new reservation. If not and the button is clicked than an error message pops up and the user must fill out the inputs.">6</A>]
</TD>
</TR>
</TABLE>

<H2 id="LENGTH6">Length 6</H2>


<H3 if="rAAAgiAAAgiAAAgiAAAgi">Prefix: 

<A href="#rAAAgiAAAgiAAAgiAAAgi">r.gi.gi.gi.gi</A></H3>


<TABLE border="2">
<TR>
<TH>Stimulus</TH>
<TH>Response</TH>
<TH>Response Trace</TH>
<TH>Equivalence</TH>
<TH>Equivalence Trace</TH>
</TR>
<TR>
<TD>
<A href="#STIMgi" title="Good Input">gi</A></TD>
<TD>
<UL>
</UL>
</TD>
<TD>
[<A href="#REQD1" title="When an input field is correctly filled out in the create new reservation page there is no observable response.">D1</A>]
</TD>
<TD>
<A href="#rAAAgiAAAgiAAAgiAAAgiAAAgi">NONE</A>
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMi" title="guest reservation information">i</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQ2" title="Only one screen can be up at a time.">2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMr" title="Make New Reservation Button Press">r</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQ2" title="Only one screen can be up at a time.">2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR>
<TD>
<A href="#STIMsr" title="Submit New Reservation Button">sr</A></TD>
<TD>
<UL>
<LI>
<A href="#OUTPUTNewReservation" title="Submit The New Reservation Button">NewReservation</A>
</LI>
</UL>
</TD>
<TD>
[<A href="#REQ6" title="All 5 input fields must be filled out to make a new reservation. If not and the button is clicked than an error message pops up and the user must fill out the inputs.">6</A>]
</TD>
<TD>
<A href="#rAAAgiAAAgiAAAgiAAAgiAAAsr">r.sr</A>
</TD>
<TD>
[<A href="#REQ6" title="All 5 input fields must be filled out to make a new reservation. If not and the button is clicked than an error message pops up and the user must fill out the inputs.">6</A>]
</TD>
</TR>
</TABLE>

<H2 id="LENGTH7">Length 7</H2>


<H3 if="rAAAgiAAAgiAAAgiAAAgiAAAgi">Prefix: 

<A href="#rAAAgiAAAgiAAAgiAAAgiAAAgi">r.gi.gi.gi.gi.gi</A></H3>


<TABLE border="2">
<TR>
<TH>Stimulus</TH>
<TH>Response</TH>
<TH>Response Trace</TH>
<TH>Equivalence</TH>
<TH>Equivalence Trace</TH>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMgi" title="Good Input">gi</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQ5" title="The create reservation screen comes up when the user clicks on the new reservation button on the home screen. It has 5 inputs to be filled out: Guest name, phone number, room type, arrival date, and departure date. The screen also has a create reservation button.">5</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMi" title="guest reservation information">i</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQ2" title="Only one screen can be up at a time.">2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR BGCOLOR="#B$CFEC">
<TD>
<A href="#STIMr" title="Make New Reservation Button Press">r</A></TD>
<TD>
ILLEGAL
</TD>
<TD>
[<A href="#REQ2" title="Only one screen can be up at a time.">2</A>]
</TD>
<TD>
ILLEGAL
</TD>
<TD>
[]
</TD>
</TR>
<TR>
<TD>
<A href="#STIMsr" title="Submit New Reservation Button">sr</A></TD>
<TD>
<UL>
<LI>
<A href="#OUTPUTNewReservation" title="Submit The New Reservation Button">NewReservation</A>
</LI>
</UL>
</TD>
<TD>
[<A href="#REQ7" title="If all 5 input fields are filled and the user hits the create reservation button than the user is returned to the home screen where the new reservation appears in the list of current reservations.">7</A>]
</TD>
<TD>
<A href="#rAAAgiAAAgiAAAgiAAAgiAAAgiAAAsr">&lt;lambda&gt;</A>
</TD>
<TD>
[<A href="#REQ7" title="If all 5 input fields are filled and the user hits the create reservation button than the user is returned to the home screen where the new reservation appears in the list of current reservations.">7</A>]
</TD>
</TR>
</TABLE>
<H1 id="VARIABLES">State Variables</H1>
<UL>
<LI id="VARIABLEView"><b>View</b></LI>
<UL>
<LI><b>Description:</b> There are 9 different possible states for the software. Each time an input is filled in or a button pressed the state is updated to a different value.</LI>
<LI><b>Possible Values:</b> 
[Home, CreateReservation, ViewReservation, 1InputGood, 2InputGood, 3InputGood, 4InputGood, Error, 5InputGood]</LI>
</UL>
</UL>
<H1 id="CSA">Canonical Sequence Analysis</H1>

<TABLE border="2">

<TR>
<TH>Canonical Sequence</TH>
<TH>View</TH>
</TR>
<TR>
<TD>
<A href="#&lt;lambda&gt;">&lt;lambda&gt;</A>
</TD>
<TD>View = Home</TD>
</TR>
<TR>
<TD>
<A href="#i">i</A>
</TD>
<TD>View = ViewReservation</TD>
</TR>
<TR>
<TD>
<A href="#r">r</A>
</TD>
<TD>View = CreateReservation</TD>
</TR>
<TR>
<TD>
<A href="#rAAAgi">r.gi</A>
</TD>
<TD>View = 1InputGood</TD>
</TR>
<TR>
<TD>
<A href="#rAAAsr">r.sr</A>
</TD>
<TD>View = Error</TD>
</TR>
<TR>
<TD>
<A href="#rAAAgiAAAgi">r.gi.gi</A>
</TD>
<TD>View = 2InputGood</TD>
</TR>
<TR>
<TD>
<A href="#rAAAgiAAAgiAAAgi">r.gi.gi.gi</A>
</TD>
<TD>View = 3InputGood</TD>
</TR>
<TR>
<TD>
<A href="#rAAAgiAAAgiAAAgiAAAgi">r.gi.gi.gi.gi</A>
</TD>
<TD>View = 4InputGood</TD>
</TR>
<TR>
<TD>
<A href="#rAAAgiAAAgiAAAgiAAAgiAAAgi">r.gi.gi.gi.gi.gi</A>
</TD>
<TD>View = 5InputGood</TD>
</TR>
</TABLE>
<p>The canonical sequence analysis has been completed.</p>
<H1 id="STATEBOX">State Box Specification</H1>
<A href="#STIMgi"><H3>Stimulus: gi, Good Input</H3></A>

<TABLE border ="2">
<TR>
<TH colspan="1">Initial State
<TH rowspan="2">Response
<TH colspan="1">Final State
</TR>
<TR>
<TH><A href="#VARIABLEView">View</A>
<TH><A href="#VARIABLEView">View</A>
</TR>
<TR CLASS=illegal>
<TD>Home
<TD>illegal
<TD>&nbsp;
<TR CLASS=illegal>
<TD>ViewReservation
<TD>illegal
<TD>&nbsp;
<TR>
<TD>CreateReservation
<TD>null
<TD>1InputGood
<TR>
<TD>1InputGood
<TD>null
<TD>2InputGood
<TR>
<TD>Error
<TD>null
<TD>1InputGood
<TR>
<TD>2InputGood
<TD>null
<TD>3InputGood
<TR>
<TD>3InputGood
<TD>null
<TD>4InputGood
<TR>
<TD>4InputGood
<TD>null
<TD>5InputGood
<TR CLASS=illegal>
<TD>5InputGood
<TD>illegal
<TD>&nbsp;
</TABLE>
<A href="#STIMi"><H3>Stimulus: i, guest reservation information</H3></A>

<TABLE border ="2">
<TR>
<TH colspan="1">Initial State
<TH rowspan="2">Response
<TH colspan="1">Final State
</TR>
<TR>
<TH><A href="#VARIABLEView">View</A>
<TH><A href="#VARIABLEView">View</A>
</TR>
<TR>
<TD>Home
<TD>
<A href="#OUTPUTReservationInfo">ReservationInfo</A>
<TD>ViewReservation
<TR CLASS=illegal>
<TD>ViewReservation
<TD>illegal
<TD>&nbsp;
<TR CLASS=illegal>
<TD>CreateReservation
<TD>illegal
<TD>&nbsp;
<TR CLASS=illegal>
<TD>1InputGood
<TD>illegal
<TD>&nbsp;
<TR CLASS=illegal>
<TD>Error
<TD>illegal
<TD>&nbsp;
<TR CLASS=illegal>
<TD>2InputGood
<TD>illegal
<TD>&nbsp;
<TR CLASS=illegal>
<TD>3InputGood
<TD>illegal
<TD>&nbsp;
<TR CLASS=illegal>
<TD>4InputGood
<TD>illegal
<TD>&nbsp;
<TR CLASS=illegal>
<TD>5InputGood
<TD>illegal
<TD>&nbsp;
</TABLE>
<A href="#STIMr"><H3>Stimulus: r, Make New Reservation Button Press</H3></A>

<TABLE border ="2">
<TR>
<TH colspan="1">Initial State
<TH rowspan="2">Response
<TH colspan="1">Final State
</TR>
<TR>
<TH><A href="#VARIABLEView">View</A>
<TH><A href="#VARIABLEView">View</A>
</TR>
<TR>
<TD>Home
<TD>
<A href="#OUTPUTCreateReservation">CreateReservation</A>
<TD>CreateReservation
<TR CLASS=illegal>
<TD>ViewReservation
<TD>illegal
<TD>&nbsp;
<TR CLASS=illegal>
<TD>CreateReservation
<TD>illegal
<TD>&nbsp;
<TR CLASS=illegal>
<TD>1InputGood
<TD>illegal
<TD>&nbsp;
<TR CLASS=illegal>
<TD>Error
<TD>illegal
<TD>&nbsp;
<TR CLASS=illegal>
<TD>2InputGood
<TD>illegal
<TD>&nbsp;
<TR CLASS=illegal>
<TD>3InputGood
<TD>illegal
<TD>&nbsp;
<TR CLASS=illegal>
<TD>4InputGood
<TD>illegal
<TD>&nbsp;
<TR CLASS=illegal>
<TD>5InputGood
<TD>illegal
<TD>&nbsp;
</TABLE>
<A href="#STIMsr"><H3>Stimulus: sr, Submit New Reservation Button</H3></A>

<TABLE border ="2">
<TR>
<TH colspan="1">Initial State
<TH rowspan="2">Response
<TH colspan="1">Final State
</TR>
<TR>
<TH><A href="#VARIABLEView">View</A>
<TH><A href="#VARIABLEView">View</A>
</TR>
<TR CLASS=illegal>
<TD>Home
<TD>illegal
<TD>&nbsp;
<TR CLASS=illegal>
<TD>ViewReservation
<TD>illegal
<TD>&nbsp;
<TR>
<TD>CreateReservation
<TD>
<A href="#OUTPUTReservationError">ReservationError</A>
<TD>Error
<TR>
<TD>1InputGood
<TD>
<A href="#OUTPUTReservationError">ReservationError</A>
<TD>Error
<TR>
<TD>Error
<TD>
<A href="#OUTPUTReservationError">ReservationError</A>
<TD>Error
<TR>
<TD>2InputGood
<TD>
<A href="#OUTPUTReservationError">ReservationError</A>
<TD>Error
<TR>
<TD>3InputGood
<TD>
<A href="#OUTPUTReservationError">ReservationError</A>
<TD>Error
<TR>
<TD>4InputGood
<TD>
<A href="#OUTPUTNewReservation">NewReservation</A>
<TD>Error
<TR>
<TD>5InputGood
<TD>
<A href="#OUTPUTNewReservation">NewReservation</A>
<TD>Home
</TABLE>
</HTML>

