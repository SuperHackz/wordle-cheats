# Wordle Bookmarklet

A simple JavaScript bookmarklet that fetches the daily solution for Wordle from The New York Times website. This bookmarklet provides the solution.

## How to Use

1. **Add the Bookmarklet**: Copy the JavaScript code below and create a new bookmark in your browser. Paste the code into the URL field of the bookmark.

   **Bookmarklet Code**:
   ```javascript
   javascript:(function(){const host='www.nytimes.com';const currentLocation=location.host;if(currentLocation===host){const year=new Date().getFullYear();const month=new Date().getMonth()+1;const day=new Date().getDate();const url='https://www.nytimes.com/svc/wordle/v2/'+year+'-'+(month<10?'0'+month:month)+'-'+day+'.json';fetch(url).then(response=>response.json()).then(data=>{alert('Solution: '+data.solution+'\nMade by SuperHackz');}).catch(err=>console.error(err));}else{alert('You must run this on the Wordle page.');}})();
