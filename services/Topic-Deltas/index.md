---

copyright:

Accrete LLC 
  
years:  2017

lastupdated: "2018-2-20"

---

Function Name: 
      
            listCompanies

Description: 

API call to get a list of companies for which we have earnings calls loaded in the DB. The return value is a JSON list of company tickers. These company tickers are to be used for CompanyName in all the other API calls 

Input Parameters: 

URL:  http://169.60.176.152:8088/listCompanies

 Method: GET 

eg:  :  http://169.60.176.152:8088/listCompanies    

Output Format:  
[   
"PCAR",
"GSK",    
"GILD",    
"KO",    
"BIDU",    
"ATVI",    
"ICE",    
"NAV",    
"CMI",    
"GT",    
"CHRW",    
"ADI",    
"EQIX",    
"FLIR",    
"GOOG",    
"AMD",    
"FMC",    
"MOS",    
"HCP",    
"AAPL",    
"MO",    
"TAP",    
"CBS",    
"AEE",    
"IFF" 
]  

_______________________________________________________________________________________________________________________________________________________________
Function Name: 
 
              callsForCompany 

Description: 

API call to get all the dates for which we have earnings calls for a company. The Company Name to be used here is the “ticker” that is returned by the list Companies call. 

Input Parameters: 

URL: http://169.60.176.152:8088/callsForCompany/<companyName> 

Method: GET 

eg:  http://169.60.176.152:8088/callsForCompany/MO 

Output Format: 
_______________________________________________________________________________________________________________________________________________________________

 [  
      {    
           "company_code": "MO",      
           "date_curr": "2017-10-26",      
           "date_prev": "2017-07-27",      
           "q_period": "Q3-2017"  
      },   
      {     
          "company_code": "MO",      
          "date_curr": "2017-07-27",      
          "date_prev": "2017-05-02",      
          "q_period": "Q2-2017"  
      },    
      {     
         "company_code": "MO",      
         "date_curr": "2017-05-02",      
         "date_prev": "2017-02-01",      
         "q_period": "Q1-2017"   
      },    
      {     

        "company_code": "MO",      
        "date_curr": "2017-02-01",      
        "date_prev": "2016-10-27",      
        "q_period": "Q4-2016"   
      },   
      {    
        "company_code": "MO",     
        "date_curr": "2016-10-27",      
        "date_prev": "2016-07-27",      
        "q_period": "Q3-2016"   
     },   
     {     
        "company_code": "MO",      
        "date_curr": "2016-07-27",      
        "date_prev": "2016-04-29",      
        "q_period": "Q2-2016"   
     },    
     {     
         "company_code": "MO",      
         "date_curr": "2016-04-29",      
         "date_prev": "2016-01-28",      
         "q_period": "Q1-2016"   
     }
]   

_______________________________________________________________________________________________________________________________________________________________


Function Name: 

          getDelta 

Description: 

API call to get delta between two earnings calls for a company. The output is a JSON which has a list of concepts, each having aggregate sentiment scores for previous and current quarter, along with the sentences that mention the concept in previous and current calls 

Input Parameters: 

URL:  http://169.60.176.152:8088/getDelta/<companyCode>/<date_prev>/<date_curr>  

Method: GET 

Eg. http://169.60.176.152:8088/getDelta/MO/2016-07-27/2016-04-29 

Output Format:  
{   
     "earnings": {     
          "aggregate_curr": -0.008946670657601241,      
          "aggregate_prev": -0.07428203377131404,      
          "list_curr":  [     
             [        
                 "Altria is off to an excellent start in 2016, growing adjusted diluted earnings per share by 14.3% despite a tough 2015 comparison.",          
                  0.42264973081037416      
            ],       
            [        
                "In beer, Altria recorded reported equity earnings from our SABMiller investment of $66 million, down from $134 million last year.",         
                 -0.22474487139158894      
            ],        
            [        
                "Please review the forward-looking and cautionary statements section at the end of today's earnings release for various factors that could cause actual results to differ materially from projections.",         
                -0.22474487139158894      
              ]      
           ],      
          "list_prev":   [      
             [         
                "Altria Group delivered strong 2016 second quarter and first half results, growing adjusted diluted earnings per share by 9.5% in the second quarter and by nearly 11% for the first half.",          
                0.2928932188134524       
            ],        
            [         
               "As noted in our earnings release, our guidance does not yet include the impact of the expected lag because the transaction remains subject to certain approvals and the closing date has not yet been determined.",         
              -0.2909944487358056       
            ],       
           [         
              "Please review the forward-looking and cautionary statement section at the end of today's earnings release for various factors that could cause actual results to differ materially from projections.",         
              -0.22474487139158894       
            ]     
        ]   
    },    
    "inventory":  {     
        "aggregate_curr": 0.1339745962155614,      
        "aggregate_prev": 0.09836180945970127,      
        "list_curr":    [       
            [         
              "PM USA's volume did even better than the industry decline rate due to modest share gains, though the growth was flattered a bit by an additional shipping day and trade inventory movements.",         
               0.1339745962155614       
            ] 
            ],      
            "list_prev":   [      
                [         
                   "In the second quarter last year, the trade built inventory ahead of excise tax increases in several states that went into effect in the next quarter.",           
                    0.42264973081037416       
             ],         
             [        
                   "This growth in 2015 benefited from higher reported volumes at PM USA driven by stable industry volume and a trade inventory build influenced by upcoming cigarette excise tax increases.",          
                   0.5527864045000421       
            ],        
            [        
                  "PM USA's reported domestic cigarette shipment volume declined 5% in the second quarter, primarily driven by the industry's rate of decline and trade inventory movements.",         
                  -0.2909944487358056      
           ],        
           [        
                 "So when adjusted for these inventory movements, PM USA estimates its second quarter cigarette volume declined 3%, in line with PM USA's estimate for the total industry decline rate.",        
                 -0.2909944487358056      
           ]     
        ]   
    },    
   "pricing":  {     
        "aggregate_curr": 0.3577714748119133,      
        "aggregate_prev": 0.33614538947909295,      
        "list_curr":   [      
            [         
                  "In the smokeless product segment, adjusted OCI margins expanded by 2.4 percentage points to 65.5%, driven principally by higher net pricing.",                
                   0.2928932188134524      
            ],        
            [        
                  "Adjusted operating companies income grew 16.7%, driven by higher net pricing and higher volume, which benefited from the national expansion of Copenhagen Mint and modest overall share gains.",          
                   0.42264973081037416      
            ]     
        ],      
       "list_prev":  [       
            [         
                  "Adjusted OCI margins expanded by 2.6 percentage points in the second quarter to over 50%, primarily driven by higher net pricing and lower SG&A costs, partially offset by higher resolution expenses.",         
                  0.2928932188134524      
            ],       
            [         
                  "In the Smokeless Products segment, adjusted OCI margins expanded in the second quarter by nearly 3 percentage points to 69.3% and by 2.6 percentage points to 67.5% for the first half, primarily driven by higher net pricing, partially offset by mix due to higher popular price product volume.",         
                   0.42264973081037416      
            ]     
        ]   
     },    
     "products":    {     
        "aggregate_curr": 0.16359935941074588,      
        "aggregate_prev": 0.3902106028111437,      
        "list_curr":   [   
           [         
                  "In the smokeless product segment, adjusted OCI margins expanded by 2.4 percentage points to 65.5%, driven principally by higher net pricing.",           
                   0.2928932188134524      
           ],        
           [        
                  "In innovative tobacco products, Altria continues to invest in developing a leading portfolio of products to meet evolving adult tobacco consumer preferences.",          
                   0.42264973081037416       
           ],        
           [         
                  "On the heated tobacco platform, our work with Philip Morris International on an FDA application for a modified-risk tobacco product claim remains on plan.",          -0.22474487139158894       
           ]    
        ],      
        "list_prev":   [    
            [        
               "In the Smokeless Products segment, adjusted OCI margins expanded in the second quarter by nearly 3 percentage points to 69.3% and by 2.6 percentage points to 67.5% for the first half, primarily driven by higher net pricing, partially offset by mix due to higher popular price product volume.",          
                0.42264973081037416       
            ],       
            [        
               "On the heated tobacco platform, our work with Philip Morris International on its FDA applications for pre-market authorization and a modified-risk tobacco product destination remains on plan, and we're making excellent progress on commercialization strategies for the U. S. market.",          
                0.42264973081037416      
            ]     
        ]  
    },  
    "revenue":  {    
       "aggregate_curr": 0.42264973081037416,      
       "aggregate_prev": 0.3577714748119133,     
       "list_curr":   [       
           [         
              "Adjusted operating companies income grew 16.7%, driven by higher net pricing and higher volume, which benefited from the national expansion of Copenhagen Mint and modest overall share gains.",          
               0.42264973081037416      
          ]     
       ],      
      "list_prev":   [     
       [        
            "Our core tobacco businesses continued to produce very strong results, with yet another solid quarter of income and retail share performance.",         
             0.2928932188134524      
       ],       
       [         
            "Our Smokeless Products segment continued to deliver excellent income performance, robust volumes, and strong share growth on Copenhagen and Skoal combined.",            
              0.42264973081037416      
       ]   
     ]   
  } 

}