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
     <li> <b> If you have to read to the operations</b> </li>
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

   
