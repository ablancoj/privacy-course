# Anonymization library

The availability of individual data is crucial for researchers; yet, legal frameworks such as the recent EU GDPR state that personally identifiable information cannot be released unless
it is subjected to anonymization; which prevents the identities of subjects from being associated with the released data, while preserving utility as much as possible. 
The members of the Universitat Rovira I Virgili (URV) have developed and implement a python library for the properly anonymization of data to be published. 
The anonymization models currently implemented in the library are: k-anonymity, t-closeness and differential privacy. The anonymization algorithms currently implemented in the library are: 
MDAV, Microaggregation and Individual Ranking.
 
The correct use of the implemented libraries for the anonymization of data needs a previous training by the user. 
The user needs to know how to apply the methods and algorithms offered by the libraries, how to apply it to different data types, understand and know how to apply the privacy parameters required by the methods 
and how to calculate metrics to evaluate the utility and privacy of the anonymized data. 
To this end, the URV members intend to develop and make available training resources consisting of a jupyter notebook for the anonymization library which will show step by step how to properly 
anonymize a data set, how to indicate the required privacy parameters and how to evaluate the resulting data.
 
In the next chapter, we have included the training notebook which will offer, in a didactic way, the experience of properly anonymize data sets and how affect the selection of the parameters applied 
in the methods to the utility and privacy of the resulting data. 
This training notebook will be public available as Jupyter notebook that will be able for downloaded to be executed locally. 
 
## Prerequisites

The input dataset is a CSV formatted file where each row corresponds to a record and each column corresponds to an attribute. 
Within the CSV file, a first line (header) stating the name of the attributes is required in order to map the attributes to features in the configuration file. 
The software does not currently support missing data points. Hence, preprocessing would be needed to either remove records with missing values or replace missing values by averages. 

The dataset configuration parameters are specified in an XML file, so that they can be reused for several datasets that share the same schema (see Dataset description section).

### Configuration parameters

The parameters needed to configure the anonymization system are stored in an XML file. 
This xml file stores parameters necessary to the configuration of the different parts of the anonymization system, so that the system can support
different attribute types.
This notes describe how to fill this xml file in order to properly configure
the anonymization process and how to configure different attribute types.

In this xml file it is described the dataset to be anonymized. Datasets to
be anonymized are persistent in disk and they are loaded from standard CSV
files. The protected dataset are also stored in CSV format.
Specifically, the CSV format consist of a file where the first row
correspond to the header and each successive row correspond to a data record.
Each record consist of one or more attribute values separated by commas.
The header of the CSV file consist of the name of the attributes also
separated by commas.

The description of the dataset consist of the relation of the attributes
in the dataset and, for each attribute, its name, its sensitivity type and
its attribute type. Following, each parameter is described.
name: This parameter indicates the name of the attribute to be configured.
The attribute name has to match with the attribute name in the header of
the dataset.

sensitivity_type: indicates the sensitivity of the attribute. The possible
sensitivity_type values are:
* identifier: the attribute unambiguously identifies the subject
* quasi_identifier: the attribute can identify the subject if it is combined with information of other attributes
* confidential: the attributes that contain sensitive information
* non_confidential: the rest of attributes

attribute_type: As it name indicates, This parameter inform about the data type
of the attribute. The current supported attribute type values are:
* numerical_discrete: natural numbers
* numerical_continuous: decimal numbers
* date: date in format dd/mm/yyyy
* plain_categorical: textual values
* semantic_categorical_wordnet: semantic nominal values
* coordinate: coordinate location, format: (lat, lon), [lat, lon] or "lat:lon"
* datetime: date and time in format: yyyy-mm-dd hh:mm:ss

Optionally, it can be indicated the min and max values of the attribute domain, when they are known
for example min=0, max=100 for age. If these values are not indicated, the domain boundary will be calculated
in function of the input data of the attribute.

An example of attribute description in XML is as follows:

```
<schema>
	<attribute
		name="date"
		sensitivity_type="quasi_identifier"
		attribute_type="date">
	</attribute>
	<attribute
		name="occupation"
		sensitivity_type="quasi_identifier"
		attribute_type="plain_categorical">
	</attribute>
	<attribute
		name="native-country"
		sensitivity_type="quasi_identifier"
		attribute_type="semantic_categorical_wordnet">
	</attribute>
	<attribute
		name="age"
		sensitivity_type="quasi_identifier"
		attribute_type="numerical_continuous"
		min_value="0"
		max_value="100">
	</attribute>
	<attribute
		name="hours-per-week"
		sensitivity_type="quasi_identifier"
		attribute_type="numerical_discrete"
		min_value="1"
		max_value="99">
	</attribute>
	<attribute
		name="income"
		sensitivity_type="confidential"
		attribute_type="numerical_discrete"
		min_value="0">
	</attribute>
	<attribute
		name="location"
		sensitivity_type="quasi_identifier"
		attribute_type="coordinate">
	</attribute>
	<attribute
		name="datetime"
		sensitivity_type="quasi_identifier"
		attribute_type="datetime">
	</attribute>
</schema>
```	