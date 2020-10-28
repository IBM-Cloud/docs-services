---

copyright:

  years:  2020

lastupdated: "2020-10-15"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About B2T Service
{: #gettingstarted}

The B2T Service (Book-to-Tax) is to calculate corporate income taxes from accounting book data, fully automatically. It is powered by the world's first and only B2T Engine that contains rates and rules of accounting and tax, and thus a user does not have to be concerned with them. 

Users can manually submit individual calculation requests at [taxmeter.com](https://www.taxmeter.com), or programmatically submitting to the corresponding Web API interface.

![Documentation image](https://mp.s81c.com/pwb-production/3ca5787c2035dd55ad7b960565f5b1a1/B2tContext-700x525-8a497840-eef1-4092-bcee-0469b45beadc_8632786b-05f8-47ad-a5b1-d36a2f91dac8.jpg)


{:shortdesc}

## Getting started

The B2T Service takes the common request/response approach: user prepares an Excel file containing the input data of the request (input file), and the results from the service will also be in an Excel file containing the output data of the response from the calculation (output file). Most of the user’s work to use the service is to prepare the input file.

To create an input file, it is the easiest to start from an example input file, and modify the data in the file to reflect your actual situation. The input file allows you to enter the most basic info of your company, specify jurisdictions to calculate taxes for, map your accounts to the Standard Tax Sensitized Chart (STSC), and enter the trial balances of your accounts for the accounting period to calculate taxes for. Notice, you do not need to enter any rates and rules of accounting and tax, because the B2T Engine has them.

After the calculation, you will be given an output file, containing the taxes (in the form of tax journal entries) for each of the jurisdictions and each of the companies specified in the input file. In addition, the output file also contains many intermediate data used during calculation. In particular, the critical book-to-tax adjustments for each account balance are in the output file, so that they can be used in your other income tax processes, such as tax provision, tax returns, tax planning, and audit defense. 

Below, a simple one-company calculation example is used to illustrate the basic usage of the B2T Service.


- Go to [www.taxmeter.com](https://www.taxmeter.com).
- Download the example input file, SingleBasic.xlsm, and save it on your computer.

There are several example files on the web site. Here we pick the simplest one, which contains input data to calculate corporate income tax for one company (R) that has to pay tax to one  jurisdiction (USA),  for the accounting period from 1/10/2019 through 4/10/2019.
  



- Review the input file just downloaded, SingleBasic.xlsm. 
- Modify nothing, or change some data (that is not in boldface) to reflect your situation
- Save the changed file

The example input file is complete and functional by itself, and so you may choose to modify nothing and leave it as is to submit for calculation. Or you may choose to modify some data just to make the exercise more interesting. 

Here are the quick overviews of the 3 main sheets in the file, which contain records and their data fields. Detailed descriptions about the type of records and data fields are stored as notes of the corresponding cells and so you may hover your cursor on a cell to see the descriptions. 

- **SetupInput sheet** - It contains data that are entered once and usually do not change often, for example, the basic info about the companies (their ownership relationships, for more complex entity structures), the jurisdictions that they have tax obligations to, the accounts of their accounting books and their mappings into the Standard Tax Sensitized Chart (STSC).  

- **RecurringInput sheet** - It contains data that are specific to the accounting period for which the taxes are to be calculated, and they are usually different from one period to the next. For example, the beginning and the ending dates of the accounting period, the trial balances for each account, and for more complex situations, currency exchange rates, apportionment rates to be used. 

- **OutputDataRef sheet**  - It contains descriptions of the data fields in an output file. In addition to the final result of taxes calculated (the highlighted fields), an output file contains a lot of intermediate data that reveals the calculation logic, the accounting/tax rates and rules used, and user messages from the B2T Engine. These data are highly valuable for many other common income tax processes, such as tax provision and tax returns. The output reference sheet serves as a data dictionary for users to further take advantage of the calculation results.

It is perhaps not surprising that the majority of the input data records are for entering trial balances. One helpful tip for new users is to enter records of account mappings and account balances in small groups, adding a few more accounts for each calculation. The engine does not require a complete accounting book to perform the calculation. This is very helpful to build up confidence in the engine’s calculation logic, and to allow quickly locating any unexpected results. Users can then either choose to override the engine’s logic, or contact support (support@taxmeter.com) to request an explanation or a new feature.

- Go to [www.taxmeter.com](https://www.taxmeter.com).
- For Step 1 on the page, choose the input file that you were working with: SingleBasic.xlsm
- For Step 2 on the page, click the “Submit …” button
- [Wait for B2T Engine to complete processing, a link to the output file will be shown]
- For Step 3 on the page, click the output link displayed to download the output file

On a Windows computer, an even easier way to submit for calculation is to go to the “RecurringInput” sheet of the input file, and locate the “Submit…” button at the top of the sheet. Just click it, and the whole input file will be sent to B2T Engine. The button does not work on a Mac computer, and some company may not allow an Excel file to connect to the internet.

The output file from the B2T Engine is also an Excel file. The first few sheets are copies of the input file, so that the results can always be correlated to the input data. The output data are in their own tabs, whose tab color is different from that of the input tabs for easy identification. Again, the data dictionary for the output data is in the “OutputDataRef” sheet.
The primary, and the focal, sheet of the output is “OutputSummary”. It contains all the final results (in highlighted cells): the total tax expense and its current and deferred portions, for each entity’s tax obligations. Further, the sheet also points to other detailed sheets that provide all the intermediate data of the calculation, including the critical book-to-tax adjustments for each account and their adjustment logic. Colored arrows are the shortcuts to navigate back-and-forth between output sheets.  


That’s it. It is indeed quite simple and easy to calculate taxes from accounting data using the world’s first and only B2T Engine. Notice that you never provided any rates and rules of accounting and tax, the Engine has them. You can override the logic if you choose to (which is beyond the scope of this writing). 

Further notice how fast the Engine performs the calculation. The Engine is accessible via a Web API, you can obtain your own API key to programmatically submit the calculation requests to your dedicated Engine resources. You can do so by subscribing to the B2T Service, for as low as $1 a month. This way your accounting, tax, ERP, EPM, or other corporate systems can obtain accurate tax data at any time, as opposed to waiting until the quarter- or year-end. The real-time calculation of corporate income tax is now reality.     


[The End]



