# SSML Tool

SSMLTool is a demonstrator for examining SSML support using the W3C Web Speech Synthesis API.  Two approaches
are demonstrated:

* In-line SSML transmitted directly to an SSML supporting synthesizer via the Web Speech API
* A "data attribute" model where SSML properties and elements are encoded using attributes, with the javascript used to consume
and insert the SSML into the text sent to the Web Speech API.

For Apple platforms that do not support SSML, but do have their own speech markup, a subset of SSML is transformed from the data 
attributes to the Apple speech markup and then sent to Web Speech.

