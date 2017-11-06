---
permalink: /settings/
layout: layout
title: Settings
---

<h1 class="center"> Settings </h1>

## Reftagger

<!-- RefTagger Control Panel -->
<div id="lbsRefTaggerCP">
<div id="lbsHeader">
<a href="http://www.logos.com/reftagger">Bible Options</a></div>
<div id="lbsVersionContainer">
<select id="lbsVersion">
        <option value="AB">AMP</option>
        <option value="ASV">ASV</option>
        <option value="DAR">DARBY</option>
        <option selected="selected" value="ESV">ESV</option>
        <option value="GW">GW</option>
        <option value="HCSB">HCSB</option>
        <option value="KJV">KJV</option>
        <option value="LEB">LEB</option>
        <option value="MESSAGE">MESSAGE</option>
        <option value="NASB">NASB</option>
        <option value="NCV">NCV</option>
        <option value="NIV">NIV</option>
        <option value="NIRV">NIRV</option>
        <option value="NKJV">NKJV</option>
        <option value="NLT">NLT</option>
        <option value="TNIV">TNIV</option>
        <option value="YLT">YLT</option>
      </select>
    </div>
<div id="lbsLibronixContainer">
<input id="lbsUseLibronixLinks" type="checkbox"/>
      <label for="lbsUseLibronixLinks">Show Logos Links</label>
    </div>
<div id="lbsSaveContainer">
<input id="lbsSave" onclick="javascript:refTagger.lbsSavePrefs()" type="button" value="Save" />
      </div>
</div>
<!-- End RefTagger Control Panel. For more info visit http://www.logos.com/reftagger. -->
