# System-Design
I have created this repo for understanding the Basics of System Design. I have taken reference from Sudo Code Youtube Channel of Yogita Sharma

<h4> What is System Design </h4>
   <p> A System is composed of Databases ,Load Balancers, Caches , Applications, Client Interfaces, Network Requests, Security Layer and Infarstrucrure. </p>
<br>
<h2> Component of System Design </h2>
      <ul><b>Logical Entities </b>
          <li> Data </li>
          <li> Databases </li>
           <li> Applications </li>
          <li> Cache </li>
           <li> Messages Queues </li>
          <li> Infra </li>
           <li> Communication </li>
          <li> Databases </li>
      </ul>
      <br>
       
 <ul><b>Tangible Entities</b>
          <li> Text , Images , Videos </li>
          <li> MongoDB, MySql , Cassandra </li>
           <li> Java , Golang, Python </li>
          <li> Redis , Memecache </li>
           <li> Kafka , RabbitMQ </li>
          <li> AWS , GCP , Azure </li>
           <li> API's , RPC , Messages</li>
      </ul>
<img src='/System design_1.jpg' height='500px' width='500px'/>

<i> Application or Services in the form of Mobile Application or Desktop Application or Web Application</i>

<h3> Now we have some Questions </h3>
     <ul>
     <li> <b> How do people or User interact with DataBases </b></li>
     <li> <b> If you have to read to the DataBases</b> </li>
     <li> <b> If you have to write to the DataBases</b> </li>
     <li> <b> If you have to fetch the information from the DataBases and store the some information in the DataBases</b>
     </li>
     </ul>

<p> For that We have Application or services Layer in the form of <b> Mobile App , WEB Application , Desktop Application </b></p>
      
      
<i>In previous Image we was running our Database and Application in Same Machine </i>   

<p>In Second Image if DataBase is running on a different machine and Application is running on Diffrent machine then we need communication Protocol</p>

<h1> Communication Protocol</h1> 
<p>It Ensure that component of system can interact with each other </p>

<b> if Database is executed on different machine ans Application is executed on different machine
    so how they will connected it will connected by the help of communication protocol.</b>
<i> Similarly if Application wants to connect with another application that can connect by Request API /RPC 
    etc. </i>    

<img src='/new image_1.jpg' height='500px' width='500px'/>

<p> Here you can see that DataBase is running on Different machine and we connected our Application with Database by using of Communication Protocol, if our application wants to connect with some another application in same machine we can connect through <b> Request API/RPC</p>
</p>

<b><i> It is not necessary that we should have Presentation Layer like Application like Logger System that not contain any Presentation Layer because where we was only saving the data in the form of info and debug </i></b>

<i>Presentation Layer like WEB Application, Mobile Application, Desktop Application </i>

<img src='/image.jpg' height='500px' width='500px'/>


<h1>Calender System </h1>

<p>

alendar system ka low-level design (LLD) samajhne ke liye, hum iske main components ko samjhenge aur unke beech interactions ko diagram ke zariye dekhne ki koshish karenge. Is LLD mein, hum classes ka design, unke relationships, aur functionalities ko samjhenge.

1. Main Components (Entities):
User:
Yeh system ka core user hota hai jo apne events ko manage karta hai. Har user ke multiple events ho sakte hain, jaise meetings, reminders, etc.




Event:
Event wo cheez hoti hai jo ek specific date aur time par user ke liye schedule hoti hai. Ek event ka type meeting, task ya reminder ho sakta hai.

Reminder:
Yeh ek notification hoti hai jo user ko event se pehle alert karne ke liye hoti hai.




Calendar:
Calendar user ke saare events ko ek jagah manage karta hai. Har user ka apna calendar hota hai, aur us calendar mein events store hote hain.




Attendee:
Attendee wo log hain jo kisi meeting ya event mein shaamil hote hain.



2. Low-Level Design (Classes)
User Class:
Yeh class user ka data represent karti hai, jaise uska naam, email, aur uske events ka list.






class User {
    private String userId;
    private String name;
    private String email;
    private List<Event> events;

    public User(String userId, String name, String email) {
        this.userId = userId;
        this.name = name;
        this.email = email;
        this.events = new ArrayList<>();
    }

    public void addEvent(Event event) {
        events.add(event);
    }

    public List<Event> getEvents() {
        return events;
    }
}


Event Class:
Event ke details ko define karta hai, jaise start time, end time, description, attendees, etc.

java
Copy code

public class Event {
    private String eventId;
    private String title;
    private String description;
    private Date startTime;
    private Date endTime;
    private EventType eventType;
    private List<Attendee> attendees;
    private Reminder reminder;

    public Event(String eventId, String title, String description, Date startTime, Date endTime, EventType eventType) {
        this.eventId = eventId;
        this.title = title;
        this.description = description;
        this.startTime = startTime;
        this.endTime = endTime;
        this.eventType = eventType;
        this.attendees = new ArrayList<>();
    }

    public void addAttendee(Attendee attendee) {
        attendees.add(attendee);
    }
}




Reminder Class:
Reminder event ke liye ek notification set karta hai jo event ke pehle user ko yaad dilata hai.




java
Copy code

public class Reminder {
    private String reminderId;
    private int minutesBeforeEvent;
    private ReminderType type;

    public Reminder(String reminderId, int minutesBeforeEvent, ReminderType type) {
        this.reminderId = reminderId;
        this.minutesBeforeEvent = minutesBeforeEvent;
        this.type = type;
    }

    public void sendReminder(User user, Event event) {
        // Logic to send reminder (email, SMS, etc.)
    }
}

Attendee Class:
Attendee class us user ko represent karti hai jo kisi event mein participant hai.




java
Copy code

class Attendee 
{
    private String name;
    private String email;

    public Attendee(String name, String email) {
        this.name = name;
        this.email = email;
    }
}

3. Class Diagram Explanation
Let's break down the relationships:

User: Har user ke paas ek calendar hoga jo multiple events ko manage karega.
Event: Har event ka ek title, time, aur attendees ka list hota hai. Event types (Meeting, Reminder) alag-alag ho sakte hain.
Attendees: Attendees class define karti hai ki kaun log event mein part le rahe hain.
Reminder: Reminder events ke saath attached hota hai taaki user ko time se pehle notification mil sake.
4. Class Diagram
Yeh diagram aapko classes ke relations samjhne mein madad karega:

plaintext
Copy code
+--------------------+        +-------------------+       +-------------------+
|      User           |        |       Event       |       |    Reminder       |
+--------------------+        +-------------------+       +-------------------+
| - userId: String    |        | - eventId: String |       | - reminderId: Str |
| - name: String      |        | - title: String   |       | - minutesBefore:  |
| - email: String     |        | - startTime: Date |       | - type: Enum      |
| - events: List<Event>+---+    | - endTime: Date   |       +-------------------+
+--------------------+   |    | - attendees: List  |         |
                          |    +-------------------+         |
                          |           ^                       |
                          +-----------|-----------------------+
                                      |
                                +------------+
                                |  Attendee  |
                                +------------+
                                | - name     |
                                | - email    |
                                +------------+
5. Process Flow (High-Level):
Create User: Calendar system mein ek naya user create hota hai.
Add Event: User apne calendar mein ek naya event schedule karta hai (meeting, task, etc.).
Add Attendees: Event mein attendees ko add kiya jata hai.
Set Reminder: Event ke liye ek reminder set kiya jaata hai jo user ko event ke pehle notify karega.
6. Sequence Diagram:
plaintext
Copy code
User      ->  Calendar System
1. Create Event    : Request to create event
2. Add Reminder    : Set reminder for event
3. Add Attendees   : Invite attendees to the event
4. Notify Reminder : Reminder triggers notification
7. Flow Diagram Explanation:
Jab user calendar mein ek event create karta hai, system us event ko user ke calendar mein add karta hai.
Event ke saath, user ek reminder bhi set karta hai jo event ke start hone se pehle notify karega.
Attendees ko invite karne ke baad, system unhe bhi notify karta hai jab event aane wala hota hai.
Yeh LLD ek basic calendar system ko cover karta hai. Future enhancements ke liye features jaise recurring events, timezone management, aur external calendar integration add kiye ja sakte hain.
   
</p>

   
