---

TITLE


---  1.5'


Who is this guy? 

What is he going to talk us about?
   
   a good way be close to your users. 


---  2.5'
??


have you ever been this guy?  << pics of loadin image >>
or this guy ? << pic of 500 >>

we all have been there, and the experience ranges from annoying to mildly frutrating


people expetcs FAST resonsiveness from ANY online content, from ANY app. 
It doesnt matter if you are selling the coolest sneakers, if you have the best pasta recipes or your tax advices are the best:  
there is little more irritating than a site that feel slugghis, than an app that feels like it's taking time off of you life (it might actually want to do that, but fast enough so you won't question it!)   ( show raging at pc gif)  


      <= 100ms – user feels the system is reacting instantaneously
      <= 1 second – user feels their flow of thought is uninterrupted
      <= 10 seconds – user’s attention will stay on task

          under XXX ms, ppl feels is an uniterrupted flow
          under YYY ms, ppl attention is still enganged
          over  ZZZ  ms, you lost them man. 


So we need to serve content fast. 
There are several things that we can do - improve the compression, have powerful servers, and enough of them provisioned, and have as strong as a network as possible (for what we can control)  

but there is something else that can be done and is it can be surprisingly easy to set up in certain enviroments




                                    things have gone centralising, to then needing to be closer to the edge. Its a pulse. 


                                    ?? verify history list??

                                    Mainframes -> PC -> Heavy Client -> Thin Clinet/Fat servers -> network got faster and faster but : 

                                    - SCALE, so many clients - ALL OVER the place


---  3'
??

let me tell you a story.  I had joined the company only by a few days when...
  
 BAD EXAMPLE  ??

       fb -> got us hammered. could not cope well with the incoming traffic
       
       (( see also tax lems story . -- tey where rising too many instaces in autoscaling. common solution could have been add a reverse proxy and modify the code to point static content to the CDN. With CND on the goog LB and path matching, this was done all at LB level w/o code changes and with one click))
  
        -- our site arch.
    
               LB
           EC2 . EC2 
              RDS


then
    -- > CDN - with akamai 
    
could have opted for autoscaling the EC2s but there was not really the need for it, CDN seemd better option in terms of costs (and was already adopted company wide, just needed to add a context to it  - and rewrite the links to static content to point to cdn. maybe this is the most painful thing. I will show you tho, that is not necessarly always the case!)



---  1'

??

 What's a CDN is and how it Works


CDNs became an essential tool to successfully conduct business online for one main reason: the Internet was not originally architected to do all of the amazing things that it does today! It simply wasn’t built to handle the demands of massive amount of data, live high definition video, flash sales, and large downloads that people expect today. CDNs were specifically built to make the Internet work better, deliver media at scale, and to enable all of the connected experiences you can imagine.

In specific terms, CDN technology should provide the following primary benefits to a business: 

Performance 
Availability 
Security


https://www.akamai.com/uk/en/cdn/what-are-the-benefits-of-a-cdn.jsp

https://www.globaldots.com/9-benefits-using-cdn/


https://cloud.google.com/cdn/   




---  3'
??

Helps you with: 
 - closer to user to respond faster 
 
?? - distribute load geographically ( some do Anycast )
   -> larger surface for DDoS attacks
   
 - and offload origin servers 
 
 




---  2'

Many cdn's out there, here's some:

  Cedix report: 
  https://www.cedexis.com/google-reports/
 

---  5'
 
  Demo: 
  
  enable CDN on GCP LB + GCS
  
  so remeber when I told you that we had to rewrite the pointers to our static content, now hosted by a CND?
  Turns out, if we were on goog platform this would not have been necessary. You can enable Goog CDN configuring the LoadBalancer for any given backend (and this can be a pool of servers as a GCS bucket! ) 
  
  All you need to do to activate the CDN is

      tick a box
      define some path rules
      Enjoy low latency
  
  

      show stackriver latency graphs ??

      show graph
      
      https://github.com/leontr/demo/blob/master/Screen%20Shot%202018-12-04%20at%201.23.58%20pm.png . 

      https://medium.com/google-cloud/how-good-is-google-clouds-cdn-e181a16f0404 
  

---  1'

?? 

what issues solves . // wrap up

with litteraly just one click you can have:

 - closer to user to respond faster 
 
?? - distribute load geographically ( some do Anycast )
   -> larger surface for DDoS attacks
   
 - and offload origin servers 



---  5'

 Q&A 
 
---
