# CeneoScraper

## Algorithm for extracting opinions about single product from Ceneo.pl
1. Access the first page of the product using requests
2. Turn the page into html soup
3. Using html tags and classes, extract every needed aspect of the review
4. Repeat for every review on the page
5. Repeat for every page by changing the base-url in a loop
6. Save data in a database of one's choosing for later use

## Structure of a single opinion on Ceneo.pl
|Component|Variable|Selector|
|---------|--------|--------|
|opinion|opinion|div.js_product-review:not(.user-post--highlight)|
|opinion ID|opinion_id|['data-entry-id']|
|opinion’s author|author|span.user-post__author-name|
|author’s recommendation|recommend|span.user-post__author-recomendation > em.recommended|
|score expressed in number of stars|stars|span.user-post__score-count|
|opinion’s content|content|div.user-post__text|
|list of product advantages|pros|div.review-feature__item--positive|
|list of product disadvantages|cons|div.review-feature__item--negative|
|how many users think that opinion was helpful|helpful|button.vote-yes['data-total-vote']|
|how many users think that opinion was unhelpful|unhelpful|button.vote-no['data-total-vote']|
|publishing date|published|span.user-post__published > time:nth-child(1)['datetime']|
|purchase date|purchased|span.user-post__published > time:nth-child(2)['datetime']|
