# Stories

In this section we set the context for the rest of the workshop.

## Elisabeth: Paired Exploring/Automating

I was a member of the team developing Bringlight, a web application for charitable giving.
Although I was the least skilled developer on the team, I was the most skilled at
exploratory testing. 
Periodically if we were odd, I would solo on exploring the site to find problems.
It turned out pairing on exploring was even more beneficial, however.

One day when my pair and I had just wrapped up a feature and had about half and hour
before lunch, we decided to spend time exploring. 

"I have an idea," I said. "I want to see if we're vulnerable to code injection."

"Wut?" said my pair. 

"Here, I'll show you," I said. The web app allowed users to create a profile with their
name and a short bio. New users were displayed prominently on the home page. I created
a user with `<script>alert("Hi!");</script>` as the bio. Sure enough, when we 
navigated to the home page an alert box cheerfully greeted us with "Hi!"

"But why would anyone ever do that?" my pair asked.

My pair was an incredibly capable developer, but did not have a lot of
experience with security-related concerns. I explained about hackers and cross-site scripting attacks.

I tried another example and was rewarded with yet another "Hi!" It seemed our web app was
indeed very vulnerable. I suggested that after lunch we write some automated tests around cross-site scripting. My pair agreed.

When we returned from lunch, I was ready to write some very traditional looking test automation to ferret out more instances of cross-site scripting vulnerabilities. My pair was not hampered by tradition.

"We have these test data fixtures," he said. "Why bother writing tests to insert bad data when we can put the bad data right in the existing test data and then run the existing tests? Any place we have a cross site scripting bug will result in failing tests." 

My suggestion would have taken at least a day to implement. His took all of 10 minutes. In under half an hour we had discovered dozens of places in the code where we had vulnerabilities and needed to html escaping content provided by users. Within another couple hours we had fixed them all.

If this had been a traditional project where I was doing after-the-fact QA I would have found each of those places through laborious trial and error, filed each one as a separate bug, and the developers would have fixed them one at a time. Because we were an Agile project we would never have done that. But even as an Agile project, if I had not been pairing with a developer, I still would have used a brute-force method to discover the vulnerabilities instead of learning a much more elegant approach. My pair and I both learned a great deal in a short amount of time, all because we were a pair with wildly diverse backgrounds.

## Elisabeth: Pairing with Designers

When I was building Entaggle, I worked with a designer on the color scheme and layout. The first designer I worked with was accustomed to mocking things up in Photoshop. I didn't want to waste any time on static mockups. I just didn't have the budget to pay him to mock things up, iterate on the mockups, and then iterate on the actual site. I wanted to sketch quickly to establish a direction, then iterate right on the site itself.

My designer was not at all comfortable pairing. He did not feel fluent with CSS; he was much more in his comfort zone in Photoshop. One could argue that this was a serious skill gap in my designer. However, I had enough CSS/SASS understanding for both of us; he had the aesthetic and UX sense that I lacked.

I pushed my designer to pair with me. I drove. He didn't so much "navigate" as suggest layouts and assess the results. We were able to lay out the basics in half a day of pairing instead of spending multiple calendar days going back and forth on the design.

In the end my designer reported that I pushed him hard outside his comfort zone, but that he was able to see the design take shape so much more quickly, and was able to see what was and was not working so much faster, that being uncomfortable was worth it.