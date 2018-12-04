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

       fb -> got us hammered    (( see also tax lems story))
  
        -- our site arch.
    
               LB
           EC2 . EC2 
              RDS

then
    -- > CDN - with akamai 



---  1'

??

 What's a CDN is and how it Works



 A Content Delivery Network is a network or caches at the edge


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


      show box to tick 

      show stackriver latency graphs ??

      show graph

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
