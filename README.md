# DocLangTranslator

## Getting Started With Azure Translator Service

This service helps us to translate documents from one language to another and at the same time, it retains the formatting and the structure of the source document. So, let’s say, if any text in the source document is in italics, then the newly translated document, will also have the text in italics.

## Key Features of Translator Service

Let’s have a look at a few of the key features, of the Translator service,

- Auto-detection of the language of the source document
- Translates large files
- Tanslates multiple files in a shot
- Preserves formatting of the source document
- Supports custom translations
- Supports custom glossaries
- Supported document types – pdf, csv, html/htm, doc/docx, msg, rtf, txt, etc.
- Implementation can be done using C#/Python as SDKs are available. Supports REST API too.

## How to Translate 

To perform this entire translation process, here are the major steps, one needs to take care of,

###### Step 1

The first step is to login into the Azure portal and creates an instance of the Translator service.
![This is an image](/storage/emulated/0/DCIM/Screenshots/IMG_20220310_204740.jpg)
Clicking on Create will open up a new page, furnish all the details and click on the Review + Create button. Doing this will create an instance of a Translator service.

###### Step 2

Grabbing the key and the endpoint of the Translator service,

###### Step 3

Create an instance of Azure Storage service as we need to create two containers.

The first container named inputdocs - holds source documents, which need to be translated
The second container named translateddocs - holds target documents, which are the translated documents
Once containers are created, you could see them listed under your storage account as shown below:

###### Step 4

Upload all the documents which need to be translated, under inputdocs container.

###### Step 5

Next is to generate the SAS tokens for both source and target containers. Note that the source container must have at least Read and List permissions enabled, whereas the target container must have Write and List permissions enabled while generating SAS. Below are the steps to generate SAS token for the source document.

Similar steps need to be performed for the target container too.

###### Step 6

Now comes the C# code, which utilizes all the information from the above steps,

###### Step 7 - Sample input(English) and output document(French)

On executing the above C# code, you will notice that translated files got added to translateddocs container as shown below,
