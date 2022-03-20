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
![Screenshot (2)](https://user-images.githubusercontent.com/73302381/158076385-329ca9ef-2bcf-4336-a842-2afeb6c0e993.png)
Clicking on Create will open up a new page, furnish all the details and click on the Review + Create button. Doing this will create an instance of a Translator service.
![1647196327576](https://user-images.githubusercontent.com/73302381/158074436-d3b6c30a-bf57-461a-9577-eeb5b9565283.jpg)

###### Step 2

Grabbing the key and the endpoint of the Translator service,
![1647196327569](https://user-images.githubusercontent.com/73302381/158074461-d5bffea0-2ceb-4c06-abd5-c7b54e401825.jpg)

###### Step 3

Create an instance of Azure Storage service as we need to create two containers.
![1647196327562](https://user-images.githubusercontent.com/73302381/158074510-15578501-70a8-4560-a0f5-b1c98ffee115.jpg)
-The first container named inputdocs - holds source documents, which need to be translated
-The second container named translateddocs - holds target documents, which are the translated document
-Once containers are created, you could see them listed under your storage account as shown below:

###### Step 4

Upload all the documents which need to be translated, under inputdocs container.
![Screenshot (1)](https://user-images.githubusercontent.com/73302381/158076372-38211f97-de63-4323-8681-50b509231ed9.png)

###### Step 5

Next is to generate the SAS tokens for both source and target containers. Note that the source container must have at least Read and List permissions enabled, whereas the target container must have Write and List permissions enabled while generating SAS. Below are the steps to generate SAS token for the source document.
![1647196327555](https://user-images.githubusercontent.com/73302381/158074549-f5c65af1-9182-44a9-b025-f0ab8184f0bb.jpg)
Similar steps need to be performed for the target container too.
![1647196327549](https://user-images.githubusercontent.com/73302381/158074601-a2a80e0d-6ea6-401d-8857-0d10ac52d182.jpg)

###### Step 6

Now comes the C# code, which utilizes all the information from the above steps.
![Screenshot (3)](https://user-images.githubusercontent.com/73302381/158076457-ee3018f2-c1a6-4cfb-8378-6bfa9fe573b2.png)

###### Step 7 - Sample input(English) and output document(French)

On executing the above C# code, you will notice that translated files got added to translateddocs container as shown below.
![Screenshot (9)](https://user-images.githubusercontent.com/73302381/159168062-4f2199e2-d6e1-4976-a360-73ccabedec23.png)
