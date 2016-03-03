# archiveit-in-primo
**Title**: Integration of Archive-It results via OpenSearch API with Ex Libris Primo 

**Created by:**
> Ido Peled<br/>
> Solutions Architect Manager<br/>
> Ex Libris, a ProQuest Company <br/>
> ido.peled@exlibrisgroup.com <br/>

**Revised by:**
> Lily Pregill <br/>
> Techne Library Consulting <br/>
> lily@technelib.com <br/>

**Date:** March 3, 2016

**Background:** This solution was developed by Ex Libris for the New York Art Resources Consortium (NYARC) to display Archive-It results directly within the Primo user interface using the [OpenSearch API] (https://webarchive.jira.com/wiki/display/search/OpenSearch+API). NYARC's Primo instance is hosted by Ex Libris.

**Working Implementation:** [NYARC Discovery] (http://discovery.nyarc.org)

**Process:**

> Step 1: Download the example archive-it.html file containing the javascript to call the API and CSS to display the results.

> Step 2: Edit line 173 to include the institution’s Archive-It collection numbers:

```
var apiurl = "https://archive-it.org/seam/resource/opensearch?i=4472&i=4544&i=2135&i=4398&i=4614&i=4387&i=4432&i=4847&i=4958&i=4269&n=10&q=" + searchQuery.toLowerCase();
```
Collection number can be concatenated using the same i parameter and the & character in between the parameters. The example above shows 10 collections (4472, 4544, 2135, 4398, 4614, 4387, 4423, 4847, 4958, 4269)

> Step 3: Edit the CSS to fit the look-and-feel of your Primo site.

> Step 4: Save archive-it.html to the institution's Primo server under static_htmls.

> Step 5: Open Primo BackOffice administrative interface

> Step 6: Navigate to “Primo Home > Ongoing Configuration Wizards > Views Wizard”

> Step 7: Open the relevant view for editing

> Step 8: Click on “Customize Layout” from the first screen

> Step 9: Change the “Page” dropdown box to “Brief Results”

> Step 10: Click on the "contentEXL - Div"

> Step 11: Add a new tile using the "Add Tile" button on the right side of the screen

> Step 12: Click on the "new tile"

> Step 13: Change the "content" dropdown box to "Custom Tile"

> Step 14: Enter the URL of the "archive-it.html" file as placed under the static_htmls

> Step 15: Continue to deploy the changes


**Notes:**

To change default check-box behavior:

```
htmlText = "<tr id='resultsdiv' class='hideItems'>
```

remove class=’hideItems’ to default to displaying Archive-It results; also add checked to input element:

```
<input id="toggleImages" type="checkbox" name="toggleImages" value="off" class="uncheckable showhide" checked>
```
