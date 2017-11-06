---
permalink: /settings/
layout: layout
title: Settings
---

<h1 class="center"> Settings </h1>

<style>

/* ----- RefTagger CP ----- */
#lbsRefTaggerCP {
    width: 22em;
    background-color:#f7f7f7;
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4em;
    font-size: 80%;
    text-align: center;
    border-style: double;
    border-width: 2px;
}

#lbsHeader {
    text-align: center;
    font-size: 120%;
    font-weight: bold;
    border-bottom: solid #000000 1px;
    padding: .25em;
}

#lbsSaveContainer, #lbsVersionContainer, #lbsLibronixContainer {
    padding: 4px;
    display: inline;
}

#lbsSave {
    border:1px solid gray;
    font-family: helvetica, arial, "sans serif";
    cursor: pointer;
}

#lbsVersion {
    font-size:100%;
}

#lbsRefTaggerCP a:link{ color:#0000ff; } 
#lbsRefTaggerCP a:visited{ color:#b400ff; } 
#lbsRefTaggerCP a:hover{ color:#0ebfe9; } 

#lbsUseLibronixLinks {
    cursor: pointer;
}

</style>

## Reftagger

<!-- RefTagger Control Panel -->
<div id="lbsRefTaggerCP">
<a href="http://www.logos.com/reftagger"></a><br />
<div id="lbsHeader">
<a href="http://www.logos.com/reftagger">Bible Options</a></div>
<br />
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
<input id="lbsUseLibronixLinks" type="checkbox" />
      <label for="lbsUseLibronixLinks">Show Logos Links</label>
    </div>
<div id="lbsSaveContainer">
<input id="lbsSave" onclick="javascript:refTagger.lbsSavePrefs()" type="button" value="Save" />
      </div>
</div>
<!-- End RefTagger Control Panel. For more info visit http://www.logos.com/reftagger. -->
