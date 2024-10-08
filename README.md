<h2>Scenario</h2>
<p>As a security professional working in a tech company, I'm required to regularly update a file that identifies the employees who can access restricted content. The file content are based on who is working with personal client records. There is an access restriction, therefore there is an allow list for IP addresses permitted to sign into the restricted subnetwork and there is also a remove list that identifies which employees you must remove from this allow list.</p>

<h2>Objective</h2>
<p></p>The goal is to create an algorithm that uses Python code to check whether the allow list contains any IP addresses identified on the remove list. If so, you should remove those IP addresses from the file containing the allow list.</p>

<h2>Solution</h2>
<b>Step 1 <br>Open the file that contain the allow list:</b>
<p><img width="817" alt="bukolasehinde" <img src="https://github.com/user-attachments/assets/71899b29-cac0-41cb-9e5c-17fbc84276c6">


</p>
<p>In the snapshot above, the 'with' statement is used with the .open() function in read mode to open the allow list file for the purpose of reading it. IP addresses that are allowed to access restricted informations are stored in the 'allow_list.txt' of the text file.<br> There are also IP addresses that should no longer have access to this information, and their IP addresses need to be removed from the text file, I assigned these IP adddresses to a variable named 'remove_list' that contains the list of IP addresses to be removed. <br>
<p>I further displayed both variables to explore their contents.<br>To open the 'allow_list.txt' file:</p>
<p>
  <img width="835" alt="bukolasehinde" src="https://github.com/user-attachments/assets/e80baa84-3c17-42b9-938a-64bdecba287f">


</p>
<p>The output gives an error because the code only contains the first line of the 'with' statement which means opening the file. Next, I'll complete the 'with' statement by reading the file's content and working on other task operations on the file.</p>

--------------------------------------------------------------------------------------------------------------------------------------------------------
<b>Step 2 <br>Reading the file contents:</b>
<p>
  <img width="432" alt="bukolasehinde" src="https://github.com/user-attachments/assets/8ca7235f-a6ea-4ab5-afc6-cce28e676686">

</p>
I used the .read() method to read the imported file which cotains the contents of the "allow_list.txt" file, and then converts into a string format
that allows me to store it in the 'ip_addresses' variable.<br>
Afterwards, I displayed 'ip_addresses' using the print() function to examine the data in the allow list.</p>

--------------------------------------------------------------------------------------------------------------------------------------------------------
<b>Step 3 <br>Converting the string into a list:</b>
<p>
  <img width="671" alt="bukolasehinde" src="https://github.com/user-attachments/assets/9e0d06b9-8630-4237-a83c-bbb486490853">

</p>
I need to convert the string into a list in order to remove individual IP addresses from the allow list. Therefore, I reassigned the ip_addresses variable using the .split() method which updated the data type from a string to a list, and later on allow me to remove some IP addresses from the allow list.<br>
Moving on, I used the print() function to display 'ip_addresses' variable for update verification.</p>

--------------------------------------------------------------------------------------------------------------------------------------------------------
<b>Step 4 <br>Iterating through the remove list:</b>
<p>
  <img width="622" alt="bukolasehinde" src="https://github.com/user-attachments/assets/2992e8bc-7aec-4efb-90ca-304af440e7fe">

I need an iterative statement to remove the elements of 'remove_list' from the 'ip_addresses' list. So I built the iterative statement (for), with a loop variable named (element), and looped through 'remove_list'.<br> Finally, I displayed each element in 'remove_list' using the print() function.

--------------------------------------------------------------------------------------------------------------------------------------------------------
<b>Step 5 <br>Removing IP addresses that are on the remove list:</b>
<p>
  <img width="546" alt="bukolasehinde" src="https://github.com/user-attachments/assets/42eea2e5-05b6-45aa-baf8-78bb7f7bf139">

</p>
IP address from the allow list, 'ip_addresses' that is also contained in remove_list are to be removed but because there were not any duplicates in ip_addresses, I was able to use the code in the snapshot above to do this.<br>
First, I created a conditional statement 'if' within the loop to evaluate if the loop variable element is in the ip_addresses list. I did this to avoid an error that might result from applying .remove() to elements that were not found in ip_addresses.<br>

Then, within conditional 'if', I applied .remove() to the 'ip_addresses' then I passed in the loop variable element as the argument so that each IP address that was in the 'remove_list' would be removed from 'ip_addresses'.

I then displayed the updated ip_addresses list using the print() function to verify that the elements of 'remove_list' are no longer in the ip_addresses list.
</p>

--------------------------------------------------------------------------------------------------------------------------------------------------------
<b>Step 6 <br>Updating the file with the revised list of IP addresses:</b>
<p>
  <img width="415" alt="bukolasehinde" src="https://github.com/user-attachments/assets/902bdd99-a460-4ed5-9759-b30b458f8dd9">

</p>
For the original file to be updated, I used the .join() method to create a string from the list ip_addresses so that I could pass it in as an argument to the .write() method when writing to the file "allow_list.txt". This is necessary because ip_addresses must be in string format when used inside the with statement to rewrite the file.

<p> The .join() method is applied to a string consisting of the character that will be used to separate every element in the iterable once its converted into a string. The .join() method takes in an iterable like a list and concatenates every element of it into a string.<br>In the snapshot above, I applied the .join() method to the string "\n". The "\n" character indicates to separate each element by placing it on a new line.This means that 'ip_addresses' is converted from a list back into a string with each IP address on a new line.</p>

<p>Finally, I built the with statement that rewrites the original file using the "w" parameter when calling the open() function. This works by to deleting the contents in the original file and replace it with the revised list of IP addresses.</p>

<h2>Summary</h2>
<p>
In this project, I have successfully developed an algorithm involves steps such as opening files and parsing their contents. Iterated through the remove list for evaluation, removing IP addresses that are on the remove list and then updating the file with the revised list of IP addresses.
</p>
