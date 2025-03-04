Title: We Have Every Free PACER Opinion on CourtListener.com
Author: Michael Lissner
Date: 2017-08-15
Tags: PACER, RECAP, Opinions, Orders, bulk data, crawling, CourtListener

<div class="right-image">
    <img src="{filename}/images/free-opinion-dropdown.png"
         alt="Free Opinion Report Dropdown"
         class="img-responsive border">
</div>


At Free Law Project, we have gathered millions of court documents over the years, but it's with distinct pride that we announce that we have now completed our biggest crawl ever. After nearly a year of work, and with support from the [U.S. Department of Labor][dol] and [Georgia State University][gsu], we have collected every free written order and opinion that is available in PACER. To accomplish this we used PACER's "Written Opinion Report," which provides [many opinions for free][free].
  
This collection contains approximately 3.4 million orders and opinions from approximately 1.5 million federal district and bankruptcy court cases dating back to 1960. More than four hundred thousand of these documents were scanned and required OCR, amounting to nearly two million pages of text extraction that we completed for this project.

All of the documents amassed are available for search in the [RECAP Archive of PACER documents][ra] and via [our APIs][api]. New opinions will be downloaded every night to keep the collection up to date.
 
<div class="left-image">
    <a href="https://www.courtlistener.com/?type=r&q=&order_by=score+desc">
        <img src="{filename}/images/twenty-million-docs-in-recap.png"
             alt="The RECAP Archive now has more than twenty million documents."
             class="img-responsive border">
    </a>
    <p class="caption">With this additional collection, the <a href="https://www.courtlistener.com/recap/">RECAP Archive</a> now has information about more than twenty million PACER documents.</p>
</div>
<div class="clearfix"></div>

As a backup and permanent repository, we are continuing our partnership with the [Internet Archive][ia], where we are in the process of uploading a copy of every opinion that we download. The Internet Archive is a mission-driven non-profit dedicated to permanently storing digital content, and we are fortunate to have their support for this initiative.

We believe that this collection of PACER documents will be an invaluable tool for legal scholars, lawyers, journalists, and the public. These documents are a critical part of America's legal system, but until now there was no free way to access or analyze these documents in bulk.

In addition to creating this collection of orders and opinions, we are also releasing a new version of our open source tool for scraping PACER data, [Juriscraper][js]. This version supports parsing PACER dockets and written opinion reports, and over time we will be adding additional features so that Juriscraper will be a flexible tool for automated data gathering on the PACER website. One of our goals at Free Law Project is to [support researchers and empiricists in their work][cs], and we are excited about the potential of this new tool.
 
The initiative to scrape, archive, and share these opinions is one of the most important in our history, and we hope that if you find this work valuable [you will support Free Law Project with a donation][donate]. Your support allows us to create and maintain projects like this and to build critical legal archives.


[ra]: https://www.courtlistener.com/recap/
[api]: https://www.courtlistener.com/api/
[announce]: {filename}why-downloading-all-free-pacer.md
[dol]: https://www.dol.gov/newsroom/releases/oasp/oasp20170112
[gsu]: {filename}dol-grant.md
[ia]: https://archive.org
[donate]: {filename}/pages/donate.md
[free]: {filename}/pacer-fee-history.md#opinions-made-free
[js]: {filename}/pages/juriscraper.md
[cs]: {filename}/pages/data-services.md

<!--
RECAPDocument.objects.filter(is_free_on_pacer=True).order_by().count()
3437674

Docket.objects.filter(docket_entries__recap_documents__is_free_on_pacer=True).distinct().count()
1520836

RECAPDocument.objects.filter(is_free_on_pacer=True, ocr_status=RECAPDocument.OCR_COMPLETE).order_by().count()
417479

RECAPDocument.objects.filter(is_free_on_pacer=True, ocr_status=RECAPDocument.OCR_COMPLETE).order_by().aggregate(Sum('page_count'))
{'page_count__sum': 1989332}

first = RECAPDocument.objects.filter(is_free_on_pacer=True).earliest('docket_entry__date_filed')

first.docket_entry.date_filed
datetime.date(1960, 4, 29)
-->
