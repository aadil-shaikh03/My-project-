# My-project-
A simple translater web
<!doctype html>
<html> 
 <head> 
  <title>translater</title> 
  <style>  
     body{  font-family: "Poppins", sans-serif;  
  background: #f3f4f6;  
  display: flex;  
  justify-content: center;  
  align-items: center;  
  height: 50vh;  
 }    
 .container {  
  background-color: white;  
   padding:23px;  
   border-radius: 3px;  
 box-shadow: 0 4px 15px rgba(0,0,0,0.1);  
  }  
 button{  
     
   /*margin-top: 15px;  */
  background-color: #2563eb;  
  color: white;  
  border: none;  
  padding: 10px 20px;  
  border-radius: 10px;  
  cursor: pointer;  
  font-size: 15px;  
 }  
 textarea {  
   margin: 40px;  
   padding: 20px;  
   border-radius:10px;  
   color: black;  
 }  
 .result {  
  background:#f9fafb;  
  margin-top: 20px;  
  padding: 10px;  
  border-radius: 10px;  
  min-height: 50px;  
  color: #333;  
 }

   </style> 
 </head> 
 <body> 
  <div class="container"> 
   <h2>language translater</h2> <textarea id="inputText" placeholder="Enter your text..."></textarea> 
   <div> <select id="sourcelang"><option value="en">english</option><option value="hi">hindi</option><option value="spa">spanish</option> <option value="mar">marathi</option> </select> <select id="targetlang"><option value="en">english</option><option value="hi">hindi</option><option value="spa">spanish</option> <option value="mar">marathi</option> &gt;</select> 
    <div> <button onclick="translateText()">Translate</button> 
    </div> 
    <div class="result" id="output.innerText">
      Translation will appear here... 
    </div> 
   </div> 
  </div> 
  <script>  
async function translateText() {  
  const input = document.getElementById("innerText").value;  
  const sourceLang = document.getElementById("sourceLang").value;  
  const targetLang = document.getElementById("targetLang").value;  
  const output = document.getElementById("outputText");  if (!input) {
output.innerText = "Please enter text to translate.";
return;
}

try {
const res = await fetch(https://api.mymemory.translated.net/get?q=${encodeURIComponent(input)}&langpair=${sourceLang}|${targetLang});
const data = await res.json();
output.innerText = data.responseData.translatedText;
} catch (error) {
output.innerText = "Error while translating.";
}
}
</script> 
 </body>
</html>