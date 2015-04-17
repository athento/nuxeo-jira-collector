# Nuxeo Jira Collector

## Synopsis

The Jira issue collector allows you to easily embed a JIRA feedback form into your own web site. This plugin adds this snippet inside your site *head* tag.

## Code Example

``` javacsript
// Add Jira Feedback 
var s = document.createElement("script");
s.type = "text/javascript";
s.src = "https://your-site.atlassian.net/...";
jQuery("head").append(s);
```

## Motivation

From Jira documentation:
> When used by people visiting your web site click this trigger tab and submit the resulting JIRA feedback form, an issue is conveniently created in JIRA.

## Installation

In order to use this plugin, you must deploy it along with [nuxeo-js-addon-enabler](https://github.com/athento/nuxeo-js-addons-enabler) and add **feedback.js** to the **custom-includes.xhtml** file.

``` xml
...
<!-- Include your own js files here from other plug-ins -->
<script type="text/javascript"
  src="#{baseURL}js/?scripts=intercom.js%7Cother-plugin.js">
</script>
...
```

When this is done, you just edit your [feedback.js](src/main/resources/web/nuxeo.war/scripts/feedback.js) and modify this line with your own information from Jira:

``` javascript
s.src = "https://your-site.atlassian.net/...";
``` 
