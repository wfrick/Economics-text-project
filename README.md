# Economics text project
 Creating a dataset of economic writing.
 
 ### Purpose
 
The purpose of this project is to create a text database of popular writing about economics. It can be used to train models to recognize economics as a topic or to analyze the topics the field of economics is concerned about.
 
 ### Source
 
This project leverages the blog Economist's View by retired economist Mark Thoma. For nearly a decade, Thoma's blog was a central curator of the economics blogosphere and so represents a good starting point for analyzing economics writing. 
 
In leveraging the Economist's View archive and the articles linked in it, without republishing them for readers, I believe this project falls within fair use. In keeping with fair use, any users of this project should not publish entire articles from this database without permission from the original publisher.
 
 ### Detail
 
 If you are just looking for the text dataset, open the Jupyter notebook 4_access_dataset.ipynb
 That will unzip the file data.zip and save the csv as "economics_text.csv". That csv is ~143mb.
 The csv has ~14,000 articles in it.
 
 If you are looking to use the code, the three Jupyter notebooks work in order:
 
 1_get_link_posts
 Requires an API key for Microsoft Bing web search, stored in a file keys.py
 Searches Bing for link recommendation posts from Economist's View and saves those urls to a csv (EV_links.csv)
 
 2_get_links_from_link_posts
 Takes EV_links (the link recommendation posts) and extracts links within each url. 
 Returns a csv of links about economics (Recs_from_EV.csv)
 
 3_get_text
 Takes Recs_from_EV as an input.
 Uses the newspaper3k package to extract text and metadata from each economics link.
 Returns a csv of all articles with text and metadata (articles_with_text.csv)
 Zips that csv as data.zip
 
 The final csv contains these fields:
 'URL', 'Title', 'Source', 'Authors', 'Summary', 'Text','Keywords', 'Publish date', 'HTML'
 
 Rows without a title and url are dropped; otherwise not all rows are complete.
 
 articles_with_text and a file called mid_loop_results aren't uploaded because of file size.