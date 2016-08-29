org.doctales.terminology 
========================

[![Build Status](https://travis-ci.org/doctales/org.doctales.terminology.svg?branch=master)](https://travis-ci.org/doctales/org.doctales.terminology)
[![license](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0)

**org.doctales.terminology** is a plugin for the [DITA-OT](http://dita-ot.github.io) for creating DITA-based terminology.
The plugin contains a new DITA `<termentry>` topic type. This topic type represents a single term.
The plugin also contains an oXygen XML authoring framework. The authoring framework simplifies editing `<termentry>` topics.

**Features**:

- Specialized DITA `termentry` topic
- Generates a terminology checker (Schematron based) to find and replace deprecated terms in your DITA files
- Generates TBX-Min and TBX-Basic files to send your terminology to your Language Service Provider (LSP)


### Installation

You can install the plugin to the DITA-OT with the following command:

```Batchfile
dita -install https://github.com/doctales/org.doctales.terminology/archive/master.zip
```


### Add &lt;oXygen/&gt; XML framework (optional)

To install the <oXygen/> XML framework, proceed as follows:

1. In <oXygen/> open the menu `Options` > `Preferences`.
2. In the preferences, open `Document Type Association` > `Locations`.
3. Add the `frameworks` directory of the plugin.
   ![framework](media/images/framework.png)


### Stylesheet

**org.doctales.terminology** ships an <oXygen/> XML framework that contains an <oXygen/> XML author mode stylesheet.
The stylesheet simplifies authoring `<termentry>` topics. The stylesheet is available in the following languages:

- English
- German


#### Example

The following code snippet shows the sample file `truck.dita`.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE termentry PUBLIC "-//DOCTALES//DTD DITA DOCTALES Termentry//EN" "termentry.dtd">
<termentry id="truck">
  <title>Truck</title>
  <definition>
    <definitionText>A truck is a motor vehicle designed to transport cargo.</definitionText>
    <definitionSource>
      <sourceReference href="https://en.wikipedia.org/wiki/Truck"
                       format="html"
                       scope="external">
        Wikipedia
      </sourceReference>
    </definitionSource>
  </definition>
  <termBody>
    <fullForm language="de-DE" usage="preferred">
      <termVariant>Lastkraftwagen</termVariant>
    </fullForm>
    <acronym language="de-DE" usage="preferred">
      <termVariant>LKW</termVariant>
    </acronym>
    <fullForm usage="preferred" language="en-US">
      <termVariant>truck</termVariant>
    </fullForm>
    <fullForm usage="notRecommended" language="en-GB">
      <termVariant>lorry</termVariant>
    </fullForm>
  </termBody>
  <relations>
    <relatedTerms>
      <relatedTerm keyref="car"/>
    </relatedTerms>
  </relations>
</termentry>
```

The screenshot shows the same file rendered with the <oXygen/> XML author mode stylesheet.

![author-mode](media/images/author-mode.png)


#### Activate the author mode stylesheet

To use the author mode stylesheet, proceed as follows:

1. Choose the style **DOCTALES Termentry** in the **Styles** menu.<br/>
   ![author-mode](media/images/styles-menu.png)
2. Turn of all tags in the **Tags** menu.<br/>
   ![author-mode](media/images/tags-menu.png)


> **Note**
>
> Use the plugin [org.doctales.termbrowser](https://github.com/doctales/org.doctales.terminology) additionally to generate a nice looking termbrowser.

Documentation: [org.doctales.terminology](http://doctales.github.io/plugins/org.doctales.terminology.html)