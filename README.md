# SpringBoot2OAuth

<p><img class="aligncenter size-full wp-image-2097 lazyloaded" src="https://i0.wp.com/javatechonline.com/wp-content/uploads/2020/12/OAuth.jpg?resize=640%2C442&amp;ssl=1" alt="How to implement OAuth in a Spring Boot Project?" width="640" height="442" data-recalc-dims="1" sizes="(max-width: 640px) 100vw, 640px" srcset="https://i0.wp.com/javatechonline.com/wp-content/uploads/2020/12/OAuth.jpg?w=903&amp;ssl=1 903w, https://i0.wp.com/javatechonline.com/wp-content/uploads/2020/12/OAuth.jpg?resize=300%2C207&amp;ssl=1 300w, https://i0.wp.com/javatechonline.com/wp-content/uploads/2020/12/OAuth.jpg?resize=768%2C530&amp;ssl=1 768w, https://i0.wp.com/javatechonline.com/wp-content/uploads/2020/12/OAuth.jpg?resize=600%2C414&amp;ssl=1 600w" data-ll-status="loaded"><noscript></p>

<h3><span id="Getting_Access_Token_from_the_Authorization_Server"><span style="color: #000080;">Getting Access Token from the Authorization Server</span></span></h3>
<p>1) The user is asking the client to access my resource from the resource server (Google Drive) and review the documents.<br>
2) The client goes to the authorization server to get access of the resources on behalf of resource owners.<br>
3) Authorization Sever will check if the resource owner wants client to access his/her resource. Also asks the resource owner what all are the resources you want client to access on your behalf.<br>
4) Resource Owner replies Yes, I am the person who wants client to access some of my particular resources.<br>
5) After getting confirmation from resource owner, the Authorization server sends an Authorization token to the client.<br>
6) Then the client asks the Authorization server for an Access Token sending the same Authorization token along with its request.<br>
7) Authorization Server provides Access Token to the client to access required resources.</p>

<h3><span id="Getting_Access_to_resources_from_the_Resource_Sever"><span style="color: #000080;">Getting Access to resources from the Resource Sever</span></span></h3>
<p>8) The client sends a request to resource Server with Access token provided by the Authorization server to access the resources of resource owner.<br>
9) Resource Server validates the Access token provided by the client with Authorization Server<br>
10) Authorization Server validates the Access token and sends confirmation to Resource Server<br>
11) Consequently Resource Server provides access of resources to the client.<br>
12) Finally, Client (Document Review Service) reviews the documents using its internal application/software and provides review comments to Resource Owner(user).</p>

<p>Your starter class of Spring Boot Project should be annotated with @EnableOAuth2Sso like below code:</p>

<p>Step#1 : Select Project, right click on it, Run as &gt; Spring Boot App<br>
Step#2 : Open Browser and hit URL : http://localhost:8081/<br>
Step#3 : You will be redirected to the Facebook page as shown below. Also observe the redirected URL of your browser which is something like <mark>https://www.facebook.com/dialog/<span style="background-color: #00ffff;">oauth?client_id=****************</span>&amp;redirect_uri=http%3A%2F%2Flocalhost%3A8081%2Flogin&amp;response_type=code&amp;state=1Gepzv</mark></p>
<p>♥ The above URL clearly indicates the magic of OAuth. 🙂</p>
<p><img class="aligncenter wp-image-2103 size-full lazyloaded" src="https://i1.wp.com/javatechonline.com/wp-content/uploads/2020/12/FBPage.jpg?resize=523%2C625&amp;ssl=1" alt="OAuth" width="523" height="625" data-recalc-dims="1" sizes="(max-width: 523px) 100vw, 523px" srcset="https://i1.wp.com/javatechonline.com/wp-content/uploads/2020/12/FBPage.jpg?w=523&amp;ssl=1 523w, https://i1.wp.com/javatechonline.com/wp-content/uploads/2020/12/FBPage.jpg?resize=251%2C300&amp;ssl=1 251w" data-ll-status="loaded"><noscript><br>
Step#4 : Click on ‘Continue as Your Name’<br>
Step#5 : Finally you will see below page with Facebook User details.</p>
<p>&nbsp;</p>
<p><img class="aligncenter size-full wp-image-2104 lazyloaded" src="https://i0.wp.com/javatechonline.com/wp-content/uploads/2020/12/FBOutput.jpg?resize=398%2C169&amp;ssl=1" alt="oAuth" width="398" height="169" data-recalc-dims="1" sizes="(max-width: 398px) 100vw, 398px" srcset="https://i0.wp.com/javatechonline.com/wp-content/uploads/2020/12/FBOutput.jpg?w=398&amp;ssl=1 398w, https://i0.wp.com/javatechonline.com/wp-content/uploads/2020/12/FBOutput.jpg?resize=300%2C127&amp;ssl=1 300w" data-ll-status="loaded"><noscript></p>
<p>Here, we are getting the user information of a facebook app even without logging into it. That’s the capability of OAuth. 🙄</p>
<p>Step#6 : Hit the URL <span style="background-color: #00ffff;">http://localhost:8081/user</span> , you will see all the details of user similar to JSON format.</p>
