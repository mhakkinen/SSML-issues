# SSML required for Assessments

## say-as

### SSML element

```There are<say-as interpret-as="ordinal">10235</say-as> people in zip code <say-as interpret-as="characters">90274</say-as>```

### Example

```In the year <span say_as="date_year">1876</span> telephone was invented.```

```The zip code is <span say_as="character">63105</span>.```

### Alternative approaches

* CSS3 Speech 'speak-as' property but not as complete as SSML say-as
* In the *wild* aria-label is seen, but introduces unacceptable braille issues

## phoneme

### SSML element
```<phoneme alphabet="ipa" ph="təˈmeɪ toʊ">tomato</phoneme>```

### HTML Example
```The <span phonetic_pronunciation="təˈmeɪ toʊ">tomato</span> is red.```

### Alternative approaches

* `aria-label` being used by some *but* the pronunciation text string is sent to *both* TTS and refreshable braille, which is unacceptable 
* Create custom dictionary entries for each AT
* Use PLS specification (requires TTS to support), does not address all contextual issues

## sub

### SSML element

```<sub alias="World Wide Web Consortium">W3C</sub>```

### HTML Example
```Common table salt is really <span substitution="Sodium Chloride">NaCl</span>.```

### Alternative approaches

* `aria-label` being used by some *but* the pronunciation text string is sent to *both* TTS and refreshable braille, which is unacceptable
* Use PLS specification (requires TTS to support), does not address all contextual issues

## emphasis

### SSML element
```That is a <emphasis level="strong"> huge </emphasis> bank account!```
  
### Alternative approaches

* Screen Readers and Read Aloud Tool could *reliably* and in a consistent manner change speech speech characteristics for emphasised text. 
  
### HTML Example
```That is a really <span emphasis="strong">huge</span> car.```

## break

### SSML element

```Take a deep <break time="3s"/>breath.```

### HTML Example
```Take a deep <span break_time="3">breath</span> then continue.``` 

### Alternative approaches

* https://www.w3.org/TR/css3-speech/#pause-props-pause-before-after
