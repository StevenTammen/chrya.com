---
permalink: /settings/
layout: layout
title: Settings
---

<h1 class="center"> Settings </h1>

<div style="margin: 0px; padding: 0px; border: 1px solid rgb(221, 221, 221); outline: 0px; font-size: 8px; vertical-align: baseline; background-color: rgb(255, 255, 255); width: 22em; font-family: Arial, Helvetica, sans-serif; line-height: 1.4em; color: rgb(51, 51, 51); text-align: center; background-position: initial initial; background-repeat: initial initial;">
<a href="http://www.logos.com/reftagger">
</a>
<div style="margin: 0px 0px 4px; padding: 0.25em; border-width: 0px 0px 1px; border-bottom-style: solid; border-bottom-color: rgb(221, 221, 221); outline: 0px; font-size: 10px; vertical-align: baseline; background-image: url(http://www.logos.com/images/reftagger/lgbg.gif); background-color: transparent; font-weight: bold; color: rgb(255, 255, 255); background-repeat: repeat no-repeat;">
Bible Options</div>
<div style="margin: 0px; padding: 4px; border: 0px; outline: 0px; vertical-align: baseline; background-color: transparent; display: inline;">
<select>
<option value="AB">AMP</option>
<option value="AsV">ASV</option>
<option value="DAr">DARBY</option>
<option value="esV" selected="selected">ESV</option>
<option value="GW">GW</option>
<option value="HCsB">HCSB</option>
<option value="KJV">KJV</option>
<option value="LeB">LEB</option>
<option value="MessAGe">MESSAGE</option>
<option value="nAsB">NASB</option>
<option value="nCV">NCV</option>
<option value="niV">NIV</option>
<option value="nirV">NIRV</option>
<option value="nKJV">NKJV</option>
<option value="nLT">NLT</option>
<option value="TniV">TNIV</option>
<option value="YLT">YLT</option>
</select>&nbsp;<wbr></div>
<div style="margin: 0px; padding: 4px; border: 0px; outline: 0px; vertical-align: baseline; background-color: transparent; display: inline;">
<input type="checkbox" style="cursor: pointer;">&nbsp;<wbr><label for="lbsUseLibronixLinks" style="margin: 0px; padding: 0px; border: 0px; outline: 0px; vertical-align: baseline; background-color: transparent;">Libronix</label></div>
<div style="margin: 0px; padding: 4px; border: 0px; outline: 0px; vertical-align: baseline; background-color: transparent; display: inline;">
<input value="save" type="button" style="border: 1px solid gray; padding: 0em 1em; background-image: url(http://www.logos.com/images/reftagger/dgsave.gif); color: rgb(255, 255, 255); font-family: helvetica, arial, 'sans serif'; cursor: pointer; background-repeat: repeat no-repeat;"></div>
<div style="margin: 4px 0px 0px; padding: 4px 4px 4px 10px; border-width: 1px 0px 0px; border-top-style: dashed; border-top-color: rgb(221, 221, 221); outline: 0px; vertical-align: baseline; background-color: transparent; line-height: 2; text-align: left;">
<div style="margin: 0px; padding: 0px; border: 0px; outline: 0px; vertical-align: baseline; background-image: url(http://www.logos.com/images/reftagger/logowhitebg.jpg); background-color: transparent; display: inline; float: right; background-position: 50% 50%; background-repeat: no-repeat no-repeat;">
<a href="http://www.logos.com/">
<img src="http://www.logos.com/images/Reftagger/transparent.gif" real_src="http://www.logos.com/images/Reftagger/transparent.gif" alt="Logos Bible Software" title="Logos Bible Software" border="0" height="19" width="64" style="margin: 0px; padding: 0px; outline: 0px; vertical-align: baseline; background-color: transparent;"></a></div>
</div>
<a href="http://www.logos.com/demo">Bible
Study Software</a></div>


## Reftagger Version Selection

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
      <label for="lbsUseLibronixLinks">Libronix</label>
    </div>
<div id="lbsSaveContainer">
<input id="lbsSave" onclick="javascript:refTagger.lbsSavePrefs()" type="button" value="Save" />
      </div>
<div id="lbsFooter">
<a href="http://www.logos.com/demo">Bible Study Software</a></div>
</div>
<!-- End RefTagger Control Panel. For more info visit http://www.logos.com/reftagger. -->
