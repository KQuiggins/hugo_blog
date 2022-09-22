---
title: "JavaScript and Security Fundamentals"
date: 2022-09-22T15:19:26-04:00
draft: false
author: "Kenneth Quiggins"
---

Today in my security fundamentals class, I learned about Organizational Units in Active Directory. I learned how to create groups of users and limit how long and what computer on the network they was able to use. This utilizes the Principle of Least Privledge approach. Only letting users have access to what is needed to complete the job.

I also learned how to use the `XMLHttpRequest()` method in JavaScript to pull data in from an API. There is a newer method called `fetch()`, but I did not use it because not all browsers support it at the moment. So far I have pulled the data in and parsed it from JSON into a JavaScript object. I am currently stuck trying to loop through the object an just return the jokes. This is my function so far.

```
document.querySelector('.get-jokes').addEventListener('click', getJokes);

function getJokes(e){
    
    const number = document.querySelector('input[type="number"]').value;

    const xhr = new XMLHttpRequest();

    xhr.open('GET', `https://v2.jokeapi.dev/joke/Any?amount=${number}`, true);

    xhr.onload = function(){
        if(this.status === 200){
            const response = JSON.parse(this.responseText);
            console.log(response);
            let output = '';

            if(response.error === 'false'){
                response.forEach(function(joke){
                    output += `<li>${joke.jokes}</li>`;
                });
            } else {
                output += '<li>Oops! Something went wrong</li>';
            }

            document.querySelector('.jokes').innerHTML = output;
        }

        
    }

    xhr.send();

    e.preventDefault();
    
}

```

