# Dates

EAC-CPF
{: .label }
## Uncertain dates
### Context
Encoding uncertain dates in `<date>`, `<toDate>`, `<fromDate>`
### Description
The attributes @certainty, @notBefore and @notAfter can be used with the `<date>`, `<toDate>`, `<fromDate>` elements to express the level of certainty of a particular date. @notBefore and @notAfter can be used to indicate the earliest and latest possible dates that an uncertain date might fall between. @certainty can be used to encode a term such as approximate, circa, or uncertain to indicate the level of certainty of the date provided. The @calendar and @era attributes are also available to provide additional information about a date.

EAC-CPF will also enable the use of the Extended Date/Time Format (EDTF), which has been included in the latest version of the ISO 8601 standard. This allows for the encoding of dates as '?', '~' and '%' ‘uncertain’ (?), ‘approximate’ (~), and ‘uncertain and approximate’ (%) within the machine-processable date in the @standardDate attribute for `<date>`, `<fromDate>` and `<toDate>`.

### Example
```xml
<dateRange>
	<fromDate notBefore="1971" notAfter="1975">around 1973</fromdate>
	<toDate standardDate="1992">1992</toDate>
</dateRange>
```

```xml
<date certainty="uncertain" standardDate="1968?">c. 1968</date> 
```

```xml
<dateRange>
	<fromDate calendar="gregorian" certainty="approximate" era="ce" standardDate="1950">1950</fromDate>
	<toDate calendar="gregorian" certainty="approximate" era="ce" standardDate="2000">2000</toDate>
</dateRange>
```
## Unknown or ongoing date ranges
EAC-CPF
{: .label }
### Context
Encoding unknown or ongoing dates. 
### Description
In some circumstances it may not be possible to include information about particular dates in an EAC-CPF instance because they are either unknown, or because a date range is ongoing. An example of an ongoing date range is a Corporate Body that continues to operate. Standalone dates may be unknown or a date range may be incomplete, for example when a date of birth is unknown. It may be important to indicate the status of these dates, rather than omitting them from the EAC-CPF instance. 

The @status attribute can be used with the `<date>`, `<fromDate>` and `<toDate>` elements, with a controlled list of values, to allow for indicating where dates - or parts of a date range - may be unknown, or where a date range is ongoing. 

The available value for <date> and <fromDate> is "unknown", and the available values for <toDate> are "unknown" or "ongoing"

### Example
```xml
<dateRange>
 	<fromDate status="unknown"/>
	<toDate toDate certainty="uncertain" standardDate="2010?">c. 2010</toDate> 
</dateRange>
```

```xml
<dateSet>
	<date standardDate="2014-07">July 2014</date>
	<dateRange>
		<fromDate standardDate="2016-09">September 2016</fromDate>
 		<toDate status="ongoing"/>
	</dateRange>
</dateSet>
```

```xml
<date status="unknown"/>
```