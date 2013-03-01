### About

jes is a javascript template engine for nodejs.

### Installation

    $ npm install jes

### Usage
    
layout.jes

    <div>
        <% include header.jes %>
        <%-body%>
        <% include footer.jes %>
    </div>

header.jes

    <div><%-title%></div>
    
footer.jes

    <div><%-copyright%></div>
    
run

    jes.renderFile('layout.jes', 
       {
         title:'JES', 
         body:'Welcome to jes!', 
         copyright:'copyright 2012'
       },
       function(err, data){
           if(err){
               console.log(err);
           }else{
               console.log(data);
           }
       }
    );
        
### API
    
    jes.compile(str, options); //return Function object
    
or

    jes.render(str, options);  //return String
  
or
   
    jes.renderFile(file, options, cb); 

### Cache

by default, cache is enabled. you can change it explicitly:
    
    jes.cache = false

### Include File

    <% include header%>

###The MIT License

Copyright ©2012 zhiyu zheng all rights reserved.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software. Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.