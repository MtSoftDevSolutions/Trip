


![ezgif com-gif-maker](https://user-images.githubusercontent.com/87912940/136728678-0a3c9bd9-dfaa-47a3-bca3-b3d7e90275c3.gif)





# Euro Trip

## Introduction
First Live Project focusing mainly on Python, Django Framework, and CRUD 
In this live project I experienced my first sprint sessions, daily standups, working with Azure, and working in a DevOps team. 
We were allowed to choose our own topic, I chose **Euro Trip** as I have always been fascinated with traveling. In this readme
I will discuss specific programming languages I used, what I accomplished, what led me to those accomplishments, what I plan to 
do in the future with this project, etc.
<br><br>
This project was created to help travellers to Europe. The project uses an API to convert currencies, has a form with fields pertaining to travel for users to fill 
out that can be stored in a dB, the app querries data from users and renders on the page what has been posted about different cities, users also have the ability
to create and delete entries, updating the dB. <br>
**Disclaimer: The pictures posted for this project only display example input and in no way does it reflect the author's feelings concerning individual cities or countries.**

## CRUD Functionality
The rest of this readme file will explain this project pertaining to the CRUD methodology.

## Create
I created a model **Location** which was my modelform with fields for pricing, locations, etc. it also has validation, choices, etc. I also created a total of **13** .html templates for this project. 

## Read
I created functionality for the app to allow the app to querry the dB and display information previous users had entered in the form. 
![fromdB](https://user-images.githubusercontent.com/87912940/136728877-ef03484a-7a30-4466-a917-9b855388ef83.png)

From this, I created a details page if the user wants more information
![details](https://user-images.githubusercontent.com/87912940/136728998-e2483de4-0398-4ad5-89d4-800a64190bb2.png)

## Update and Delete
I provided functionality that allows users to update the location and delete entries 
![update](https://user-images.githubusercontent.com/87912940/136729127-70f97dbb-d5f9-4fc8-8d82-95a5e2b267ae.png)

## API

'''' def currency(request):
    if request.method == 'GET':
        convertfrom = request.GET.get('Currency1')
        convertto = request.GET.get('Currency2')
        amount = request.GET.get('Currency3')
        print(convertfrom, convertto, amount)
        api_url = 'https://api.api-ninjas.com/v1/convertcurrency?want={}&have={}&amount={}'.format(convertto, convertfrom, amount)
        response = requests.get(api_url, headers={'X-Api-Key': 'KEYS'})
        # render to website importing json module
        if response.status_code == requests.codes.ok:
            print(response.text)
            finalcurrency = response.json()
            return render(request, 'currency.html', {
                'convertfrom': finalcurrency['old_currency'],
                'previousamt': finalcurrency['old_amount'],
                'newcurrency': finalcurrency['new_currency'],
                'finalamount': finalcurrency['new_amount']
            })
        else:
            print("Error:", response.status_code, response.text)
    return render(request, 'currency.html') 
    ''''
    This was the code for my API in views.py to convert currencies. 
    
## Skills Acquired
Through this live project I learned the value of teamwork as it applies to software development. I loved the teamwork aspect the most because it allowed me to observe how other people were approaching their projects, I loved all the creative forces at work and sharing my adventure in our daily standups. I learned more about CRUD. This was the first chance that I got to go from theoretical coursework to practical field work and I loved that. I was able to advance my understanding of Python, Django, HTML, CSS, Bootstrap, etc. I also really enjoyed branching out on my own, figuring out how to do things that I didn't know how to do before. 
    

