# DelveDebugger

# Debugging REST API server in local system (Localhost)

# First we have to compile our program with  # GC FLAGS and create the executable binary

![image](https://user-images.githubusercontent.com/80065996/149169222-4824c6f4-3ebf-49c6-8824-0658e344d37e.png)


# REST API service we compiled just now.

**Executable binary created as highlighted below**

![image](https://user-images.githubusercontent.com/80065996/149169332-aa19aba6-2241-46f8-b72c-ad5af80d264d.png)

# Install dlv and Gdlv latest version

 **go install github.com/aarzilli/gdlv@latest**
 
 **go install github.com/go-delve/delve/cmd/dlv@latest**
 
 # Install gops in goland editor
 
  **gops will provide details about go process currently running and their process id's**
  
  # Next step, run the below command to start the delve debugger in headful state 
  
   **delve debugger listens on 2345 port in our system
  
  ![image](https://user-images.githubusercontent.com/80065996/149172270-fa3a7cd5-0e8f-4a4b-9cd2-5eda05543e4b.png)
  
  Now delve debugger is open for debugging and we can provide the comments
  
  # setting breakpoints
  
  ![image](https://user-images.githubusercontent.com/80065996/149172746-0114701b-d5b9-48a6-973b-ae7fcb735347.png)


setting breakpoints on 36th row of inside function of (get all) function to recieve all the rows from the table

breakpoint set,

![image](https://user-images.githubusercontent.com/80065996/149172941-d23f04a0-daef-4818-964e-cc84b5a83235.png)

# Caution: WE SHOULD NOT START OUR SERVER BY EITHER "GO RUN" COMMAND OR "./myApp" (dot(.),slash(/) followed by .exe file).
# our go server will start automatically by delve debugger itself.

Now press enter after giving command "continue"

![image](https://user-images.githubusercontent.com/80065996/149173482-ebbddb34-7fd6-45d9-a90a-ed5675d8575d.png)


![image](https://user-images.githubusercontent.com/80065996/149174322-d709d2de-5345-4705-af53-35e3d6f07751.png)

**Now, debugger is waiting for us to hit the REST API via 'CURL' or 'Browser' or 'POSTMAN' or via 'REST API Client code'**

from Browser,

since we set breakpoint, our browser is still loading and not fetching the result, because our code stopped in between in breakpoint we set at 
line number 36

![image](https://user-images.githubusercontent.com/80065996/149174546-9ff4f248-0bd7-4c8d-bb19-c9e344fbbe70.png)

now see code stopped at breakpoint

![image](https://user-images.githubusercontent.com/80065996/149174905-d48ecce6-7f5c-43a1-bfc7-1a0e1022abb1.png)

Give command **next** to pass the cursor to next line like below

![image](https://user-images.githubusercontent.com/80065996/149175419-c249c98d-fa38-4f59-9a5e-4f4d50aaab3a.png)

we can print the variable contents using **print variablename** command like below,

![image](https://user-images.githubusercontent.com/80065996/149176008-ad9ed17f-f798-49ed-83c1-8308b39d50f3.png)


# By default delve debugger will not go inside the function calling another function. we need to use **step** command


![image](https://user-images.githubusercontent.com/80065996/149176559-921c889e-f2b6-4946-bb95-84d1990dc989.png)


![image](https://user-images.githubusercontent.com/80065996/149176844-b82264ff-8ee1-4a63-b6bf-a06da9304525.png)


# Use "stepout" command to comeout of a function to previos statement


![image](https://user-images.githubusercontent.com/80065996/149177971-2c8d124f-6329-4e81-8c63-020563047708.png)



![image](https://user-images.githubusercontent.com/80065996/149178160-dd10fdb9-2748-452b-8da0-d9e9c2c8b4f1.png)



# Delve debugger User Interface (UI) Gdlv by arsilli( use for normal packages rather than REST API modules)

Provide below command to initiate the User interface. New terminal will open with details


![image](https://user-images.githubusercontent.com/80065996/149179991-a0a549f9-24e0-485f-a490-f3c0a0612799.png)



![image](https://user-images.githubusercontent.com/80065996/149180157-a21931b9-a1c1-4b89-8fa0-57b3362f92a8.png)


![image](https://user-images.githubusercontent.com/80065996/149180441-e3409d59-8988-4125-b316-6e8d6c0ff0a1.png)


