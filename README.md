### Stpes to achive the task.
1) Open up a Google Sheet and input the desired URL into a cell. (in shared google sheet it is in Url column) 
2) Step to get the xpath.
  + Right click on our target website (on price tag) and click Inspect Element.
	+ Find the suitable tag which have proper vale of (price) element. (here it will be) 
	        
   ```
   <meta itemprop="price" content="269.99">
   ```
	
  + Copy the xpath of the element. (here it will be) 
	
  ```
  //*[@id="page-content"]/div[4]/div[2]/div[2]/div[2]/meta[4]
  ```
  
  + This copied xpath is not acurate as it is absolute. so make it as relative and more acurate here it will be like this:
		
    ``` //meta[@itemprop='price']/@content ```
    
  + Now go to google sheet and copy this xpath (//meta[@itemprop='price']/@content) into any cell. (in example sheet it is in xpath column)   + Now in google sheet select one cell where you want to extract the data and write the below formula (=importxml(url,xpath))
		
    ```
    =importxml(A2,B2)
    ``` 
	  
    It will extract the data from url based on xpath provided.(in shared google sheet it is in result_xpath column) 
	
  + Now you can add as many product page url and xpath (shared google sheet) in rest cell of Url and xpath respectivally. And drag below   
    the result_xpath formula. It will extarct the result.

	
For better understanding please go to shared google sheet and attached images. You can also play with google sheet by adding more url in cell.

### Google Sheet
[Link to Google Sheet](https://docs.google.com/spreadsheets/d/1sOTknzesHIyu4NKXSiPl1OQEX0ufxBissJfv6ofIQ50/edit?usp=sharing)
