# Krestiki-Noliki
Hello people! My first repository
Hehehehehe

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
      <link rel="shortcut icon" href="Прямоугольник 1 копия.png" type="image/x-icon">
    <title>Крестики Нолики</title>
      <meta name="viewsport" content="width=device-width , initial-scale=1.0">
  <link rel="stylesheet" href="style.css">
        <script src="https://unpkg.com/vue" charset="utf-8"></script>
      <style>
 
      </style>
    
  </head>
  <body>
                                       
     <div id="mane1">
      <div id="main" ref="header">
      
        <div id="reg">
            <h1>Введите имя игроков</h1>
            <input v-model="player1" placeholder="Игрок1">  
            
            <input v-model="player2" placeholder="Игрок2">
       
            <input type="checkbox"   v-model="x" style="max-width: 40px !important" placeholder="Игрок2" ><h2>Bot</h2>
          
                
            
     
            
            <button v-on:click="test">Начать</button>
        </div>  
      
      </div>
   
 </div>     
      <div id="app">{{message}}</div>
      
      
  <table id="table"  >      
  <tr>
         
    <td v-on:click="addxoro(0)">{{message[0]}}</td>
      <td v-on:click="addxoro(1)">{{message[1]}}</td>
      <td v-on:click="addxoro(2)">{{message[2]}}</td>
  </tr>
      <tr>
    <td v-on:click="addxoro(3)">{{message[3]}}</td>
          <td v-on:click="addxoro(4)">{{message[4]}}</td>
          <td v-on:click="addxoro(5)">{{message[5]}}</td>
  </tr>
      <tr>
    <td v-on:click="addxoro(6)">{{message[6]}}</td>
          <td v-on:click="addxoro(7)">{{message[7]}}</td>
          <td v-on:click="addxoro(8)">{{message[8]}}</td>
  </tr>
    
</table>
      <div id="namerez">{{message}} ходит</div>
   <div id="app1" v-on:click="rest" style="cursor: pointer">Начать с начала</div>   
      <script>
       
 
          
          
          
          
         var b = "x";    
    var name1
     var name2
     var xstatus
   var c = true
    var app =  new Vue({
        el:'#app',
        data:{
           message : "Сейчас " + b
    
        }
    })    

    var reg = new Vue({
        el : "#reg",
        data :
        {
         player1 : "",
            player2 : "",
            x : ''
        },
        methods:
        
        {
          test : function(){
            name1 = reg.player1
             name2 =reg.player2
              xstatus = reg.x
              console.log(name1)
              console.log(name2)
               console.log(xstatus)
              
              if(name1 != '' && name2 != ''){
                   var elem = document.getElementById("mane1")
              elem.parentNode.removeChild(elem)
                 }
          
                namerez.geter(name1,name2,xstatus)
            
          }
            
        }
    })
       
       

    setTimeout (() => { namerez.botgo1()}, 1000)


    
    
    
      var app1 = new Vue({
          el : "#app1" , 
          data:{
            
          }
          ,
          methods:{
               rest: function(){
                      Vue.set(tab.message,0,'') 
                   Vue.set(tab.message,1,'')
                   Vue.set(tab.message,2,'')
                   Vue.set(tab.message,3,'')
                   Vue.set(tab.message,4,'')
                   Vue.set(tab.message,5,'')
                   Vue.set(tab.message,6,'')
                   Vue.set(tab.message,7,'')
                   Vue.set(tab.message,8,'')
           
                   b = "x"  
             
              app.message = "Сейчас " + b 
                   if(reg.x == false)
                namerez.message =  namerez.retn1()
                   else  namerez.message =  "BOT"
              c = true
                   
                   setTimeout (() => { namerez.botgo()},1000)
           
          }
          }
         
      })
      botmode = false
          win = false
         
          
       
          
          
      var tab = new Vue({
          el: "#table",
              data:{
                  message: ["",'','','','','','','','']
              },
          methods:{
                addxoro: function(index)
              {
                  
                     if(tab.message[index] == "" && c == true && reg.x  == false)
                       
                       {
                         
                            Vue.set(tab.message,index,b) 
                            if(b == "x") b = "o"
                            else if(b == "o") b = "x"
                            app.message = "Сейчас " + b 
                            namerez.seter()
                            namerez.setindex()
                       }
                  
                  
                  else if(tab.message[index] == "" && c == true && reg.x == true)
                  {
                          
                            if(b == "o"){
                                     Vue.set(tab.message,index,b) 
                                    if(b == "o") b = "x"
                                 app.message = "Сейчас " + b 
                                    namerez.seter()
                                namerez.setindex(index)
                                
                               
                              setTimeout (() => {  namerez.botgo() }, 500)
                               
                            }
                          
                }
                    
                  
                    
                  
                   if((tab.message[0] == 'x' && tab.message[1] == 'x' && tab.message[2] == 'x') || (tab.message[3] == 'x' && tab.message[4] == 'x' && tab.message[5] == 'x') || (tab.message[6] == 'x' && tab.message[7] == 'x' && tab.message[8] == 'x') || (tab.message[0] == 'x' && tab.message[3] == 'x' && tab.message[6] == 'x') || (tab.message[1] == 'x' && tab.message[4] == 'x' && tab.message[7] == 'x') || (tab.message[2] == 'x' && tab.message[5] == 'x' && tab.message[9] == 'x') || (tab.message[0] == 'x' && tab.message[4] == 'x' && tab.message[8] == 'x') || (tab.message[2] == 'x' && tab.message[4] == 'x' && tab.message[6] == 'x') )
                        {
                            c = false
                            if(reg.x != true)
                            app.message = "Победил " + namerez.retn1() + "(x)"
                            else if (reg.x == true){
                                app.message = "Победил " + "BOT" + "(x)"
                                        }
                            win = true
                        }
                    
                    else if((tab.message[0] == 'o' && tab.message[1] == 'o' && tab.message[2] == 'o') || (tab.message[3] == 'o' && tab.message[4] == 'o' && tab.message[5] == 'o') || (tab.message[6] == 'o' && tab.message[7] == 'o' && tab.message[8] == 'o') || (tab.message[0] == 'o' && tab.message[3] == 'o' && tab.message[6] == 'o') || (tab.message[1] == 'o' && tab.message[4] == 'o' && tab.message[7] == 'o') || (tab.message[2] == 'o' && tab.message[5] == 'o' && tab.message[9] == 'o') || (tab.message[0] == 'o' && tab.message[4] == 'o' && tab.message[8] == 'o') || (tab.message[2] == 'o' && tab.message[4] == 'o' && tab.message[6] == 'o') )
                        {
                            c = false
                            if(reg.x == true)
                            {
                                app.message = "Победил " + namerez.retn1()+ "(0)"
                            }
                            
                            else if(reg.x == false) {
                                app.message = "Победил " +namerez.retn2() + "(0)"
                                    }
                            
                           
                        }
                  
                  
                  else if (tab.message[0] != '' && tab.message[1] != '' && tab.message[2] != '' && tab.message[3] != '' && tab.message[4] != '' && tab.message[5] != ''&& tab.message[6] != '' && tab.message[7] != '' && tab.message[8] != '')  
                       {

                           c = false
                            app.message = "Ничья"
                           


                        }
                        
                      
                  
                       
                } 
                        
                   
                    
                    
                }
          
      })
      proverkauser1 = true

        index1 = ""
        
    var namerez = new Vue({
         el:'#namerez',
            data:{
            message : name1
              
            },
         methods :
        {

                         geter : function( num1, num2 ,xec1)
                         {
                              n1 = num1
                              n2 = num2
                              checkx = xec1
                             if(proverkauser1 == true && reg.x == false){
                                  namerez.message = n1
                                 proverkauser1 = false;
                             }
                             else if(proverkauser1 == true && reg.x == true){
                                         namerez.message = "BOT"
                                 proverkauser1 = false;   
                                        }
                             return n1,n2

                         },
            
            
                            seter : function()
                        {
                                
                                 if(b == 'x' && reg.x == false)
                                {
                                namerez.message = n1

                                }
                                else if (b == 'o' && reg.x == false)
                                {
                                    namerez.message = n2
                                }
                             else if (b == 'o' && reg.x == true)
                                {
                                    namerez.message = n1
                                }
                            else if (b == 'x' && reg.x == true)
                                {
                                    namerez.message = "BOT"
                                   
                                }
                           
                            
                        },
                        retn1 : function()
                            {
                                return n1;

                            },
                          retn2 : function()
                            {
                                return n2;

                            },
                            
                            botgo : function(){
                                
                            if(b == "x" && reg.x == true)    
                            {
                                if(tab.message[2] == "o" && tab.message[8] == "o" && tab.message[5] == ""){
                                       Vue.set(tab.message,5,b)  ,
                                        b = "o"  
                                }
                                else if(tab.message[6] == "o" && tab.message[8] == "o" && tab.message[7] == ""){
                                       Vue.set(tab.message,7,b)  ,
                                        b = "o"  
                                }
                                 else if(tab.message[7] == "o" && tab.message[8] == "o" && tab.message[6] == ""){
                                       Vue.set(tab.message,6,b)  ,
                                        b = "o"  
                                }
                                else if(tab.message[0] == "x" && tab.message[4] == "x" && tab.message[8] == ""){
                                       Vue.set(tab.message,8,b)  ,
                                        b = "o"  
                                }
                               else if(tab.message[2] == "x" && tab.message[4] == "x" && tab.message[6] == ""){
                                       Vue.set(tab.message,6,b)  ,
                                        b = "o"  
                                }
                                else if(tab.message[3] == "x" && tab.message[4] == "x" && tab.message[5] == ""){
                                       Vue.set(tab.message,5,b)  ,
                                        b = "o"  
                                }
                                
                                else if(tab.message[2] == "x" && tab.message[5] == "x" && tab.message[8] == ""){
                                       Vue.set(tab.message,8,b)  ,
                                        b = "o"  
                                }
                                else if(tab.message[1] == "x" && tab.message[4] == "x" && tab.message[7] == ""){
                                       Vue.set(tab.message,7,b)  ,
                                        b = "o"  
                                }
                                
                                
                                else if(tab.message[4] == "")
                                    {
                                     
                                         Vue.set(tab.message,4,b)  ,
                                        b = "o"
                                    }
                               else if(tab.message[0] == "")
                                    {
                                     
                                         Vue.set(tab.message,0,b)  ,
                                        b = "o"
                                    }
                                  else if(tab.message[2] == "")
                                    {
                                     
                                         Vue.set(tab.message,2,b)  ,
                                        b = "o"
                                    }
                                  else if(tab.message[8] == "")
                                    {
                                     
                                         Vue.set(tab.message,8,b)  ,
                                        b = "o"
                                    }
                                  else if(tab.message[3] == "")
                                    {
                                     
                                         Vue.set(tab.message,3,b)  ,
                                        b = "o"
                                    }
                                  else if(tab.message[5] == "")
                                    {
                                     
                                         Vue.set(tab.message,5,b)  ,
                                        b = "o"
                                    }
                                  else if(tab.message[7] == "")
                                    {
                                     
                                         Vue.set(tab.message,7,b)  ,
                                        b = "o"
                                    }
                                 else if(tab.message[1] == "")
                                    {
                                     
                                         Vue.set(tab.message,1,b)  ,
                                        b = "o"
                                    }
                                 else if(tab.message[6] == "")
                                    {
                                     
                                         Vue.set(tab.message,6,b)  ,
                                        b = "o"
                                    }
                                
                                app.message = "Сейчас " +"o" , namerez.message = n1 
                                
                                 if((tab.message[0] == 'x' && tab.message[1] == 'x' && tab.message[2] == 'x') || (tab.message[3] == 'x' && tab.message[4] == 'x' && tab.message[5] == 'x') || (tab.message[6] == 'x' && tab.message[7] == 'x' && tab.message[8] == 'x') || (tab.message[0] == 'x' && tab.message[3] == 'x' && tab.message[6] == 'x') || (tab.message[1] == 'x' && tab.message[4] == 'x' && tab.message[7] == 'x') || (tab.message[2] == 'x' && tab.message[5] == 'x' && tab.message[9] == 'x') || (tab.message[0] == 'x' && tab.message[4] == 'x' && tab.message[8] == 'x') || (tab.message[2] == 'x' && tab.message[4] == 'x' && tab.message[6] == 'x') )
                        {
                            c = false
                            if(reg.x != true)
                            app.message = "Победил " + namerez.retn1() + "(x)"
                            else if (reg.x == true){
                                app.message = "Победил " + "BOT" + "(x)"
                                        }
                            win = true
                        }
                    
                    else if((tab.message[0] == 'o' && tab.message[1] == 'o' && tab.message[2] == 'o') || (tab.message[3] == 'o' && tab.message[4] == 'o' && tab.message[5] == 'o') || (tab.message[6] == 'o' && tab.message[7] == 'o' && tab.message[8] == 'o') || (tab.message[0] == 'o' && tab.message[3] == 'o' && tab.message[6] == 'o') || (tab.message[1] == 'o' && tab.message[4] == 'o' && tab.message[7] == 'o') || (tab.message[2] == 'o' && tab.message[5] == 'o' && tab.message[9] == 'o') || (tab.message[0] == 'o' && tab.message[4] == 'o' && tab.message[8] == 'o') || (tab.message[2] == 'o' && tab.message[4] == 'o' && tab.message[6] == 'o') )
                        {
                            c = false
                            if(reg.x == true)
                            {
                                app.message = "Победил " + namerez.retn1()+ "(0)"
                            }
                            
                            else if(reg.x == false) {
                                app.message = "Победил " +namerez.retn2() + "(0)"
                                    }
                            
                           
                        }
                                 else if (tab.message[0] != '' && tab.message[1] != '' && tab.message[2] != '' && tab.message[3] != '' && tab.message[4] != '' && tab.message[5] != ''&& tab.message[6] != '' && tab.message[7] != '' && tab.message[8] != '')  
                       {

                           c = false
                            app.message = "Ничья"
                           


                        }
                                
                            }
                               
                                
                               
                                } , 
            
                                    setindex : function(index){ index1 = index  }
                                    ,
                            
                                    botgo1 : function(){
                                            
                                            if(reg.x == true)     
                                                {
                                                 Vue.set(tab.message,4,b) , app.message = "Сейчас " +"o" , namerez.message = n1 , console.log("suka"), b = "o" , console.log(b)
                                                }
                                               
                                            
                                    
                                    }
                
            
             
         
         }
        
    })    
      </script>
   
  </body>
</html>
