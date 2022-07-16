Automated Audit of The Colorado Congressional Presinct Election by Python

Overview: 
An election was held for the US Congressional Presinct in Colorado, USA. An audit was conducted to verify the total number of votes cast, the total number of votes for each candidate, the percentage of votes for each candidate, the number of votes submitted by each county, the percentage of votes by each county, and the winner of the election.  The purpose of this program is to pilot an automated auditing program that if successful, will be used to audit other congressional districts, senatorial districts, and local elections.  The program will take the raw election results of mail in ballots, machine counted ballots, and DRE machine votes summarized into a CSV table, and analyze the election results and generate a vote count report in a text file.

Election Analysis Process and Outcome:

  * Total Number of Votes Cast
      
       The total number of votes was obtained by accessing the data via python using os.path.join, setting a total_votes counter to 0 and counting through each row of  the raw dataset for each vote.  The total number of votes was determined to be 369,711.
       
       Fig 1/2
       
       ![Fig1](https://user-images.githubusercontent.com/108313294/179325742-cde3815a-0150-42ef-b0f8-4171c2219f0d.png)
       
       ![Fig2](https://user-images.githubusercontent.com/108313294/179325752-b71d593d-6777-4b6d-9353-f1eb997023ec.png)


  * Total Number of Votes for Each Candidate

      The total number of votes for each candidate was obtained from the same accessed data and stored in a dictionary.  A for loop was used to run through each row,    with a conditional statement that determined if the candidate name stored in the third column of the CSV was in the dictionary.  If it is not, the candidates name    is added as a key to the dictionary and a vote was added as a value making a key value pair. If the candidates name is in the library, a vote was added to the         value stored under the key. Charles Casper Stockham obtained 85,213 votes, Diana DeGette obtained 272,892 votes, and Raymon Anthony Doane obtained 11,606 votes.
      
      Fig 3
      
      ![Fig3](https://user-images.githubusercontent.com/108313294/179325761-fb4c1cf2-1a3f-4364-a53d-823efdf6a8fb.png)

      
  * Percentage of Votes for Each Candidate
      
      The total number of votes for each candidate was converted into a percentage by dividing the total number of votes cast by the votes obtained by the candidates.  A for loop using the primary key of the candidate vote count dictionary as an index and divided it by the total number of votes then multiplied by 100. Formatting the string for export, the percentage was restricted to a precision of 1 decimal point, and a thousanths comma was used. Charles Casper Stockham obtained 23.0% of votes, Diana DeGette obtained 73.8% of votes, and Raymon Anthony Doane obtained 3.1% of votes
      
      Fig 4
      
      ![Fig4](https://user-images.githubusercontent.com/108313294/179325769-1fe23f0f-f26d-4c63-87aa-37dd4e6831c6.png)
      
  * Total Number of Votes for Each County

     The total number of votes by each county was determiend the same way as the total number of votes for each candidate but under a different variable.  38,855 votes came from Jefferson, 306,055 votes came from Denver, and 24,801 votes came from Arapahoe.
    
  * Percentage of Votes for Each County
    
      The votes from each county was converted into a percentage the same way as the votes for each candidate under a different variable. 10.5% of votes came from Jefferson, 82.8% of votes came from Denver, and 6.7% of votes came from Arapahoe.
      
      
  * Winner of Election 

      The winner of the election was determined by determining who had the most votes and the largest percentage of votes.  If a single candidate commanded the most votes and the majority percentage of shares, they were declared the winner.  This ensures that the analysis was conducted correctly.  If no candidate satisfied the condition, no candidate would be declared the winner. The winner of the election was determined to be Diana DeGette with 272,892 total votes, and 73.8% of all votes.
      
      Fig 5
      
      ![Fig5](https://user-images.githubusercontent.com/108313294/179325783-fba8118b-9f24-44db-b28d-0e7cb152ac25.png)
      
  * Generating a text report

      The data generated from the terminal was also used to generate a text file.  Variables were used to store the analysis summary of each part of the election.  Then exported to the text file addressed in figure 1.  See the text file for results.
      
      Fig 6
      
      ![Fig6](https://user-images.githubusercontent.com/108313294/179325791-ee697a9b-f75c-414f-87c7-f7da38967670.png)
      
 Elections Analysis Summary:
 
     The script was sucessfull in auditing and determining the winner of the election campaign.  A report of the analysis was automatically generated in the Analysis 
folder concluding that the winner was Diana DeGette with 272,892 total votes, and 73.8% of all votes.  The program piloted here can be scalled up or down depending on 
the type of election being held. Since the county and candidate count use the same code and only address different columns, both could be put in a bigger loop and used 
to automatically scale as many columns as needed such as in a large federal election.  Another change that can be made is integrating the print to .txt function 
directly into the loop to automatically scale it as well. In a federal election often there are also multiple candidates per party or multiple seats to be filled. The 
dictionary of candidates containing vote counts may instead contain additional dictionaries with various seat positions and party members.  
