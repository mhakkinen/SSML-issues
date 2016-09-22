# SSML required for Educational Assessments

## say-as
### Specification
Element: https://www.w3.org/TR/speech-synthesis/#S3.1.8
Attributes: https://www.w3.org/TR/ssml-sayas/

### SSML usage

```There are<say-as interpret-as="ordinal">10235</say-as> people in zip code <say-as interpret-as="characters">90274</say-as>```

### HTML Example

```In the year <span say_as="date_year">1876</span> telephone was invented.```

```The zip code is <span say_as="character">63105</span>.```

### Alternative approaches

* CSS3 Speech 'speak-as' property but not as complete as SSML say-as
* In the *wild* aria-label is seen, but introduces unacceptable braille issues

## phoneme
### Specification
Element: https://www.w3.org/TR/speech-synthesis/#S3.1.9

### SSML usage
```<phoneme alphabet="ipa" ph="təˈmeɪ toʊ">tomato</phoneme>```

### HTML Example
```The <span phonetic_pronunciation="təˈmeɪ toʊ">tomato</span> is red.```

### Alternative approaches

* `aria-label` being used by some *but* the pronunciation text string is sent to *both* TTS and refreshable braille, which is unacceptable 
* Create custom dictionary entries for each AT
* Use PLS specification (requires TTS to support), does not address all contextual issues
* Currently in the EPUB3 Specification using the SSML phoneme attributes. Limited uptake (production tools, some usage in Japan in reading systems).

   ```<p>
   The guitarist was playing a <span ssml:ph="beIs">bass</span> that was shaped like a <span ssml:ph="b&s">bass</span>.
   </p>
   ```

## sub
### Specification
Element: https://www.w3.org/TR/speech-synthesis/#S3.1.10

### SSML usage

```<sub alias="World Wide Web Consortium">W3C</sub>```

### HTML Example
```Common table salt is really <span substitution="Sodium Chloride">NaCl</span>.```

### Alternative approaches

* `aria-label` being used by some *but* the pronunciation text string is sent to *both* TTS and refreshable braille, which is unacceptable
* Use PLS specification (requires TTS to support), does not address all contextual issues

## emphasis
### Specification
Element: https://www.w3.org/TR/speech-synthesis/#S3.2.2

### SSML usage
```That is a <emphasis level="strong"> huge </emphasis> bank account!```
  
### HTML Example
```That is a really <span emphasis="strong">huge</span> car.```

### Alternative approaches

* Screen Readers and Read Aloud Tools could *reliably* and in a *consistent* manner change speech characteristics for emphasised text. 

## break
### Specification
Element: https://www.w3.org/TR/speech-synthesis/#S3.2.3

### SSML usage

```Take a deep <break time="3s"/>breath.```

### HTML Example
```Take a deep <span break_time="3">breath</span> then continue.``` 

### Alternative approaches

* CSS 3 https://www.w3.org/TR/css3-speech/#pause-props-pause-before-after


## Some further background

We'd like to see all three standards supported:

* SSML
* CSS3 Speech
* PLS

As all three have strengths: 

* precise, contextual author control (SSML)
* standardized spoken presentation styles, without altering content (CSS3)
* standardized pronunciation cues without altering content (PLS)

In the near term, precise author control is a critical requirement.  In education, the subject matter expert author understands the context and spoken requirement; the AT doesn't and shouldn't make assumptions.

