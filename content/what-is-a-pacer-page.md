Title: What is a "Page" of PACER Content?
Date: 2016-11-03
Author: Michael Lissner
Tags: PACER, transparency

As most readers of this blog know, PACER is a system run by the Administrative Office of the Courts (AO) that [hosts over a billion documents][b] from the Federal District and Circuit courts. The system was created in the nineties and was set up with a paywall so that you pay for every "page" of data that you receive. The idea of the fees, as established by the E-Government Act, is that the AO could use them to recoup the cost of running the PACER, but the pricing of the content has always been a bit odd. In my last post I talked about how these fees [result in an outrageous cost for PACER data][billion]. In this post, I do a deep dive into the core unit of PACER's pricing and attempt to answer the question, what ***is*** a "page" of PACER data? 

The size of PACER's fees has varied over the years, but they've always gone up, and they've always been assessed roughly as follows:

1. If you download a PDF from PACER, you pay by the page.

1. If you do a search, you pay by the number of search results returned. Because you don't know how many results a query will return, you don't know the price of a search in advance of placing it and being charged for it.
 
1. If you look at a list of documents within a case (the "docket" for that case), you pay by the number of "pages" of that docket.
 
The pricing of PDFs is pretty clear: 10 cents per page with a cap at three dollars. Got it. But the price of the dockets and of the search results is perplexing. Dockets and search results are also priced per page, but unlike a PDF, there ***are no pages***---these are webpages, not PDFs. So the question is, when I get charged for a search result or for a docket, what exactly am I paying for? How are "pages" calculated? What *is* a "page" of PACER data? 

To get to the bottom of this, I spent some time talking with the AO, and I present the results of those discussions below. But before I begin, I'll tell you the punchline: PACER is charging for content page by page, but they won't define how pages are actually measured. This gives them the capability to change how pages are computed in order to drive up their revenue. It makes them vulnerable to lawsuits, and indeed such a suit is progressing in the Court of Federal Claims.[^1] 

We don't know if the underlying methods of pricing have ever changed and we probably never will, but with courts being strapped for cash, we do know that there's motivation to do so. The AO's unwillingness to discuss this topic is troubling since it forms the core of their pricing. We hope that they will consider providing more details about this question.


## Getting Towards an Answer

My inquiry about this began with a phone call to the PACER service center, where I got the following answer (paraphrasing): 

> Dockets are charged based on the number of pages that would be printed if you sent them to your printer. 

This was clearly wrong, so I pushed back: "Does that mean that if I increase my font size, I have to pay more because it would print more pages?" This stumped the person on the phone, and I was told I should send an email with my question instead. Fair enough:

> When I download a PDF, it's quite clear what a page is, but when I look at a docket or search results, it's not so clear. Is this based on the font size that I have in my browser? Is it based on the kilobytes of data that I download? Is it based on the number of characters in the HTML? I'm really trying to understand this, because it feels very arbitrary.
  
> Can you give me a more specific explanation of what a "page" is? It's at the heart of your pricing, so I hope this is a question with a simple answer.

The response I received was brief and wrong again:

<div class="left-image">
    <blockquote>
    <img src="{filename}/images/pacer-page/54-lines.png"
             alt="Email from PACER stating: One page of data is 54 lines. Those lines include spacing. It is related to the data as it is extracted, and not necessarily how it is displayed on a web page or printed out."/>
    </blockquote>
</div>
<div class="clearfix"></div>

So now I've received two answers. It's not how it's printed, it's 54 lines including spacing. No more, no less. [Despite being so precise][numbers], this also didn't make any sense, because lines can have different lengths. I asked: What if one line takes two pages to print because it's very long?

The answer:
  
<div class="left-image">
    <blockquote>
    <img src="{filename}/images/pacer-page/bytes-of-data.png"
             alt="Email from PACER stating: It is actually measured by bytes of data."/>
     </blockquote>
</div>
<div class="clearfix"></div>

Ah ha. This was the third answer I'd received, but it seemed like we were getting warmer. Bytes are a measurement of data, and so pages are measured by the amount of data they return. That sort of makes sense. But wait, how many bytes make up a page?


<div class="left-image">
<blockquote>
    <img src="{filename}/images/pacer-page/how-many-bytes.png"
             alt="Email from me, asking: Can you tell me how many bytes is considered a page?"/>
</blockquote>
</div>
<div class="clearfix"></div>

The shocking response:

<div class="left-image">
<blockquote>
    <img src="{filename}/images/pacer-page/dont-know.png"
             alt="Email from PACER stating: Unfortunately, I do not have that information."/>
</blockquote>
</div>
<div class="clearfix"></div>

I could not imagine that PACER doesn't know how big a "page" is, so I pushed again and got closer to a real answer:

<div class="left-image">
    <blockquote>
        <img src="{filename}/images/pacer-page/4320-bytes.png"
                 alt="Email from PACER stating that it's 4320 bytes."/>
    </blockquote>
    <p class="caption"><a href="https://www.pacer.gov/documents/pacermanual.pdf">Here's the manual, if you're interested</a>.</p>
</div>
<div class="clearfix"></div>

For those keeping track, we're now one phone call and three answers into this seemingly basic question, but it looks like we have an answer. 

Except:

1. If you test a docket by downloading it and then measuring how big it is, nothing adds up to 4,320 bytes, so there's still no way to know where those measurements are coming from.

2. It took two PACER service center representatives three answers and maybe a dozen emails to arrive at this answer. 

3. 4,320 bytes is perhaps the most arbitrary number imaginable (although "54 lines" is about as bad). For reference, the text of this webpage is about twice that size and an MP3 is [about 800&times; as large][avg].

I decided to set aside issues number two and three, and focus on the first issue: If we know that a "page" is now defined as 4,320 bytes, what is the thing that is being divided into "pages"? Is it the webpage? The text of the webpage? Something else?
 
The answer:

<div class="left-image">
    <blockquote>
        <img src="{filename}/images/pacer-page/two-files.png"
                 alt="Email from PACER stating there are two files generated or something."/>
    </blockquote>
</div>
<div class="clearfix"></div>

This is getting into the weeds, but it feels like what she's saying is:

1. We extract a lot of data from our database in an "original extraction file."

2. We measure this data and bill you for it.

3. We send you a subset of that data in the form of a docket.

Since at this point the AO still hadn't explained how a page was created, and since this opaque process was at the heart of the revenue model for PACER, I decided to send one more email asking about the technical details for generating the "original extraction file." Since we don't know  how these files are generated, it's possible that the AO could (accidentally or deliberately) tweak this method and thereby change PACER revenue.

When I asked about this, the next response I got was from the Senior Attorney for the Administrative Office of the Courts:

<div class="left-image">
    <blockquote>
        <img src="{filename}/images/pacer-page/atty-response.png"
                 alt="Email from PACER Senior Attorney"/>
    </blockquote>
</div>
<div class="clearfix"></div>

This was a bit of a surprise, and I must confess that this is where the story goes cold. But we can learn a few things from these interactions. First, it's important to note that it took three answers before the AO could give me a vaguely correct answer to my basic question about pricing. The first two answers were flat wrong. 

Second, the AO has no interest in being fully transparent about how their pricing works. Yes, we now know that 4,320 bytes is a "page," but we still don't know: Bytes of *what*? What *is* an "original extraction file"? (This [isn't][goog] some kind of technical term.)
 
Third, we know that if you ask about this kind of thing persistently enough, you'll be routed to an attorney. At the time when I was researching this, I was shocked to hear from an attorney in response to a help desk question, but since then, it's come to make more sense. It turns out that towards the end of last year, there was a class action lawsuit filed against the AO alleging erroneous pricing for---you guessed it---generating dockets.[^1] While I won't opine on the merits of that case (and indeed I'm not a lawyer), it is possible that the AO had wind of that case and wanted to make sure they didn't make any legal missteps while emailing with me. The timeline isn't perfect---my inquiries were in November, and the case was filed in December---but if it wasn't related, it sure was prescient.

Going forward, we believe that the AO should consider a few changes:

1. The AO should share more details about how their pricing works both internally, so their staff have the correct answers, and externally, so that the answers are easy to find by the public, not buried in a 28 page manual. Indeed, in their billing it could  say how much *data* you purchased in a month instead of how many *pages*.

2. The AO should provide transparency about how "pages" are defined. We know that they're 4,320 bytes, but we still don't know what an "original extraction file" is. Providing technical details on this would provide clarity to their pricing and would make the AO less able to make technical changes in efforts to raise revenue. Criticism like this post would be largely addressed.

3. The AO should refrain from having lawyers answer help desk questions.

We hope the AO will consider these changes, and that in the future their pricing will be more transparent.


[^1]: Among [other failings][wrong], PACER doesn't provide permalinks, so for the moment, I can't provide a link to this information. What I can do is tell you to go to [the PACER website for the Court of Federal Claims][2]. From there you can look up case number: `1:15-cv-01575-TCW`. 

    Beware: There will be opaque fees.


[b]: https://www.supremecourt.gov/publicinfo/year-end/2014year-endreport.pdf 
[2]: https://ecf.cofc.uscourts.gov/cgi-bin/ShowIndex.pl
[numbers]: http://business.camden.rutgers.edu/files/Schindler-Yalch-2006.pdf
[avg]: http://filecatalyst.com/todays-media-file-sizes-whats-average/
[wrong]: {filename}/what-is-the-pacer-problem.md
[billion]: {filename}/pacer-billion-documents.md
[goog]: https://www.google.com/search?q=%22original+extraction+file%22&ie=utf-8&oe=utf-8
