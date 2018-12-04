---

TITLE


---  1.5'
???

Who is this guy? 

What is he going to talk us about?
   
   a good way be close to your users. 


---  2.5'
???


have you ever been this guy?  << pics of loadin image >>
or this guy ? << pic of 500 >>

we all have been there, and the experience ranges from annoying to mildly frutrating


people expetcs FAST resonsiveness from ANY online content, from ANY app. 
It doesnt matter if you are selling the coolest sneakers, if you have the best pasta recipes or your tax advices are the best:  
there is little more irritating than a site that feel slugghis, than an app that feels like it's taking time off of you life (it might actually want to do that, but fast enough so you won't question it!)   ( show raging at pc gif)  



    >>> 40% of people abandon a website that takes more than 3 seconds to load. – Kissmetrics


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
???

let me tell you a story.  I had joined the company only by a few days when...
  
 BAD EXAMPLE  ??  MAYBE fasten up flight deck would be better ?

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
???

>>>>
https://www.keycdn.com/support/how-does-a-cdn-work



 What's a CDN 


      GC CDN leverages Ggle's globally distributed edge points of presence to accelerate content delivery for websites and applications served out of Google Compute Engine and Google Cloud Storage. 
      Cloud CDN lowers network latency, 
      offloads origins, 
      and reduces serving costs. 
      Once you've set up HTTP(S) Load Balancing, simply enable Cloud CDN with a single checkbox.


A content delivery network or content distribution network (CDN) is a globally distributed network of proxy servers deployed in multiple data centers.


CDNs became an essential tool to successfully conduct business online for one main reason: the Internet was not originally architected to do all of the amazing things that it does today! It simply wasn’t built to handle the demands of massive amount of data, live high definition video, flash sales, and large downloads that people expect today. CDNs were specifically built to make the Internet work better, deliver media at scale, and to enable all of the connected experiences you can imagine.


<< show pics of CND network >> 


https://www.akamai.com/uk/en/cdn/what-are-the-benefits-of-a-cdn.jsp

https://www.globaldots.com/9-benefits-using-cdn/


https://cloud.google.com/cdn/   


---  3'
???



In specific terms, CDN technology should provide the following primary benefits to a business: 


<< show pic of all req. to orging vs ditributed to pop >>




?? put following together  - 

>>> https://www.keycdn.com/support/cdn-architecture


   Performance 
         why?

   Availability 
         why? 

   Security
         Why? 
      
      

            Helps you with: 
             - closer to user to respond faster 

            ?? - distribute load geographically ( some do Anycast )
               -> larger surface for DDoS attacks

             - and offload origin servers 
 
        GCP CDN:
        > Anycast
               Serve all your content from a single IP address with low latency worldwide.
        > Invalidation
               Take down cached content in minutes.
        > http2
               Supports the new, more efficient HTTP/2 protocol in addition to HTTP/1.0 and HTTP/1.1.
        > https (ssl/tls)
               Provide your own SSL/TLS certificate to secure your content using a domain name of your choice.
        > logging
               Integrates with Stackdriver Logging to give you detailed information about each cache hit and miss.
        > Origins
               Serves content originating from Compute Engine VMs and Cloud Storage buckets. You can even mix and match multiple origins                   behind a single domain. External origin servers are not supported.
 
 
 
 
---
???
CND can be PUSH or PULL

 >>  https://www.keycdn.com/support/how-does-a-cdn-work


 Basically a key-value store 


- Cache hits, misses, fill, and egress    https://cloud.google.com/cdn/docs/overview




cache in diffrent ways:

   some rules for the content to be cached :    https://cloud.google.com/cdn/docs/caching  


   --  scheme based caching   / Cache key https://cloud.google.com/cdn/docs/best-practices  https://cloud.google.com/cdn/docs/using-cache-keys
         If your site delivers the same asset over HTTP and HTTPS, enabling the Cache Key Scheme option will allow you to cache the asset          for both use-case
         https://www.keycdn.com/support/scheme-based-caching
         
         ** warnning ** Excluding components from cache keys can cause Cloud CDN to serve content intended for one user to another. Before            excluding a component, ensure your backend service's responses do not vary based on that component.
         
   --  cookie based caching   (maybe omit, G dont support)
         Depending what you are trying to achieve, you can cache assets based on a particular cookie. For example, if you set cookies              based on which language the visitor defines when they visit your site, then the resources required to display the site in a                particular language can be cached. This is done by adding the name of your cookie variable in the Cache Key Cookie feature in a            pull zone’s advanced features.
         https://www.keycdn.com/support/cookie-based-caching
   
   --  user device based caching  (maybe omit, G dont support)
        https://www.keycdn.com/support/user-device-based-caching 
       
       
 Size
 
 Cloud CDN enforces a maximum size that varies depending on whether the origin server supports byte range requests:

5 TB (5,497,558,138,880 bytes) if the origin server supports byte range requests
10 MB (10,485,760 bytes) if the origin server does not support byte range requests
Any response with a body larger than the maximum size is not cached.
 
 https://www.keycdn.com/support/byte-range-requests



---  2'
???
Not All CDNs Are Created Equal




  Cedix report: 
  https://www.cedexis.com/google-reports/
 

---  5'
???
  Demo: 
  
  set up: 
      - creted 2 buckets on gcs, made both public, put in both a the few same pics
      - modified the metadata for the files in one of them so they were cacheble (left the other 'private') :
            gsutil -m setmeta -h "Cache-Control:public" gs://gs://myawesomepicsbucket/*
            
      - created a LB, created a backend for each bucket. for one ive enabled CND, and not for the other
 

 
  
        so remeber when I told you that we had to rewrite the pointers to our static content, now hosted by a CND?
        Turns out, if we were on goog platform this would not have been necessary. You can enable Goog CDN configuring the LoadBalancer for any given backend (and this can be a pool of servers as a GCS bucket! ) 
  
Goog Clou CDN is .. 
??? describe

<< add pics of CND networ >>


enable CDN on GCP LB + GCS 
  
  All you need to do to activate the CDN is

      tick a box
      define some path rules
      Enjoy low latency
  
 ??? decide if to show tests from 3 boxes in diverese parts of the world or show stackdriver graph on different latencies with or without cdn
  ?? check these times!! https://www.keycdn.com/blog/website-latency

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
