# archiveit-in-primo
**Title**: Intergration of Archive-It results via OpenSearch API with Ex Libris Primo 

**Created by:**
> Ido Peled<br/>
> Solutions Architect Manager<br/>
> Ex Libris, a ProQuest Company <br/>

**Revised by:**
> Lily Pregill <br/>
> Techne Library Consulting <br/>

**Date:** March 3, 2016

**Background:** This solution was developed by Ex Libris for the New York Art Resources Consortium to display Archive-It results directly within the Primo user interface using the [OpenSearch API] (https://webarchive.jira.com/wiki/display/search/OpenSearch+API).

**Process:**

> Step 1: Download the example archive-it.html file containing the javascript and CSS to call the API and display the results.
> Step 2: Edit line 173 to include the institution’s Archive-It collection numbers:


> Step 3: Save archive-it.html to the institution's Primo server under static_htmls.

'''
var apiurl = "https://archive-it.org/seam/resource/opensearch?i=4472&i=4544&i=2135&i=4398&i=4614&i=4387&i=4432&i=4847&i=4958&i=4269&n=10&q=" + searchQuery.toLowerCase();
'''

