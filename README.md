# grails-xss-sanitizer
Grails 3 plugin for sanitizing XSS from the user input. This is a port of the Grails `2.x` version by @tonyzampogna (Tony Zampogna) https://github.com/tonyzampogna/XssSanitizer

This plugin uses OWASP ESAPI library to sanitize request parameters. This reduces the risk of dangerous XSS request parameters possibly being rendered on the client.

Installation
----------

Add the following dependencies in `build.gradle`
```
dependencies {
...
    compile 'org.grails.plugins:xss-sanitizer:1.+'
...
}
```

Description
----------

This plugin will add the automatic ability to strip / clean out unwanted XSS code in the browser. The plugin strips code that comes in via the request object. Also, any Servlets will use an extend HttpServletRequest so that request parameters used from that servlet will be stripped as well.

Just adding this plugin to you project with the installation instructions above will activate it. No other actions are needed.

There is an XssSanitizerUtil class that can also be used to strip strings out.

Also, you can enable or disable it by adding a key in your Config like this:

```yaml
	xssSanitizer:
	     enabled: true
```