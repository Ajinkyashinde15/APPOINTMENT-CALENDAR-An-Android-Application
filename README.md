# APPOINTMENT-CALENDAR-An-Android-Application
Everything is to be made simple, that is folk’s expectation. Here is an application that could make work easier for user. This android application basically works silently as a background process in reading the message that a user receives. It will scan for keywords like call, message, mail, ring etc. followed by words like “me, --some name—“etc. Once a word is found, the data is collected and appended to the calendar as a reminder for the user. In this way, the risk of remembrance could be eradicated and prompt the user as a notification. As a part of further work, the application could be extended in skimming through the mails, voice calls for keywords and recording them in the calendar would make the application more effective.

LEADING EDGE:
The application’s cutting edge is its capacity in reading the data in the Message API of the phone and sweeping all the necessary words, accumulating, alternating and appending it in the form of a reminder onto a calendar. The GOOGLE company is currently working on its “INBOX” application wherein for example if a user receives an information about account details along with the amount, the INBOX application will skim the data and show a feedback of “OK”, “Amount transferred”, “Thanks” which are the normal words that we use to reply back. But the point is that there is no application that reads information from message to help the user. In this way, our application performs some sort unique operation. The heart behind this application is to plug the message API into our application and using that the as in the message is received, the body of the message is collected along with the sender so as to know the source of the message. The body is accumulated in a string and scanned for keywords. Further, when the keyword is hit, the consecutive words are scanned leaving behind spaces in order to specify the receiver’s information.
As a part of future work, the application could be expanded to allow information from voice calls by listening to the words spelled by the user and scanning the keywords again, but the application initially converges to certain slang and language.

PROCESS-PROGRESS INVOLVEMENT:
Backing up the ideas from the past papers that have been published so far, the state of art mechanism of implementation is still a question mark. So, to revoke that and continue with the past work, the application is designed and fulfilled with the ideal automatic appointment calendar.

The application is designed having three W’s: What, Why and Who.
What: is the base of the application; the basic idea behind “what” is the application going do?
Why: is to ascertain that the application is going to abide the idea and concept that satisfies some kind of logic or solve some kind of problem.
Who: is the target people who is going to use the application.
Keeping in mind the above set of questions, the application answers all the questions.
Illustrating that, answering the first question: the application is working as an automatic service to the user to add reminder notification for users.
What Why Who Figure 1
Secondly, validating the second question: the application is designed to solve a problem of risk of remembrance, thereby prompting user timely.
Finally, looking up for the third one, the set of folks that is going to use the application would be any set if users that use a smart phone and has a GPS option, as the application would not only provide a reminder but give the user the option of checking the route for the next appointment.

IMPLEMENTATION WORK:
• The first part of the application included getting the application notified when a new message is received and then retrieve the relevant data from the text message. onReceive() method of BroadcastReceiver is used for detecting incoming messages in the phone. The onReceive() method detects the SMS_RECEIVED_ACTION which then reads the message body and receives the relevant message and inserts it into the database.

• We used SQLLiteOpenHelper package to implement all the database transaction. A separate class named DatabaseHandler is created where all the database transaction methods are implemented including adding, retrieving, creating, etc.

• The application includes Android CalendarView template to display the calendar.

• Using setOnDateChangeListener method of calendar DayView activity is triggered on selection of any date. The date selected is passed on to the next activity.

• On the Dayview page the layout includes different time of the day. Appointment information is retrieved from the database for the date selected and corresponding to each appointment a button is created on the DayView page showing the time of the appointment. The button is created dynamically as per the data found in the database for the particular date and the button is aligned on the time of the appointment. On clicking on the button, ReminderView activity is triggered.

• On the ReminderView activity, the reminder details are displayed after retrieving them from the database. For instances where there are multiple reminder on the same date and time, the top entry is displayed first. On shaking the phone the consequent entries are displayed following a circular loop. This is achieved by the onSensorChanged() method from interface SensorEventListener. A formula for speed of phone shake is calculated using X,Y,Z axes of the phone and if the calculated speed is > threshold value set, the data is changed with next reminder data.

• On clicking on the View Map button, it triggers the Google map on the basis of the location present in the reminder details. To implement this google LocationManager is used to connect to google maps.
