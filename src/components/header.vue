<template>

<div>
    <nav class="navbar">
        <span class="nav-opener">
            <a @click="openclosesidenav">
                <svg width="30" height="30">
                    <path d="M0,5 30,5" stroke="#fff" stroke-width="5"/>
                    <path d="M0,14 30,14" stroke="#fff" stroke-width="5"/>
                    <path d="M0,23 30,23" stroke="#fff" stroke-width="5"/>
                </svg>
             </a>
        </span>
         
        <h1 class="title">devhost :<span style="-webkit-background-clip: text;
  -webkit-text-fill-color: transparent; background-image: -webkit-linear-gradient(276deg, #f9643d, #fe2a77);">19</span></h1>
        <ul class="navbar-nav">
            
            <li><a href="#">HOME</a></li>
            <li><a @click="gotoabout">ABOUT</a></li>
            <li><a @click="gotospeakers" >SPEAKERS</a></li>
            <li><a @click="gotosponsor">SPONSORS</a></li>
             <li><a @click="gotocontact">CONTACT</a></li>
            <button class="nav-btn">REGISTER</button>
        </ul>
        
    </nav>
    <div id="side-menu" class="side-nav">
        <a href="#">HOME </a>
        <a  @click="gotoabout">ABOUT</a>
        <a  @click="gotospeakers">SPEAKERS</a>
        <a @click="gotosponsor">SPONSORS</a>
        <a @click="gotocontact">CONTACT</a>
        <button class="side-nav-btn">REGISTER</button>
    </div>
  
</div>

</template>

<script>
import {bus} from '../main'
export default {
    name:'header', 
    props:['position'],
    data(){
        return{
            pos:{
            x:"",
            y:"",
        }
        }
    },
    components:{
      
      
    },
  methods:{
            openclosesidenav(){
          
                if(document.getElementById('side-menu').style.height === '290px'){
                    document.getElementById('side-menu').style.height = '0px';
                }
                else
                    document.getElementById('side-menu').style.height = '290px';
               
              
            },

            gotoabout(){
               bus.$emit('about-clicked');
               
                
            },
            gotospeakers(){
               bus.$emit('speakers-clicked');
               
                
            },
             gotocontact(){
               bus.$emit('contact-clicked');
               
                
            },
             gotosponsor(){
               bus.$emit('sponsors-clicked');
               
                
            }

        },
}


</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=Roboto:500');
@import url('https://fonts.googleapis.com/css?family=Open+Sans:400');
body{
    margin: auto;
    overflow: auto;
   
}
a:hover {
 cursor:pointer;
}
.nav-btn{

    border: none;
    font-family: 'Open Sans', sans-serif;
    float: right;
    font-size: 15px;
    height: 76px;
    margin: auto;
    width: 160px;
    display: block;
    background-color: transparent;
    background-image: -webkit-linear-gradient(276deg, #f9643d, #fe2a77);
    background-image: linear-gradient(174deg, #f9643d, #fe2a77);
    color: white;
}
.side-nav-btn{
    border: none;
    font-family: 'Open Sans', sans-serif;
    
    height: 76px;
    margin: auto;
    width: 100%;
    display: block;
    background-color: transparent;
    background-image: -webkit-linear-gradient(276deg, #f9643d, #fe2a77);
    background-image: linear-gradient(174deg, #f9643d, #fe2a77);
    color: white;
}
.nav-opener{
    float: right;
    margin:0;
    padding: 17px;
}
.nav-opener a {
    padding: 0;
    margin: auto;
}
.side-nav-btn,.navbar-nav a,.side-nav a,.nav-opener a:focus{
    outline: none;
}
.title{
    font-family: 'Roboto', sans-serif;
    color:white;
    display: block;
    font-size: 35px;
    padding: 15px 0 0 25px;
    margin: 0;
    float: left;
} 


.navbar{
    z-index: 1;
   background-color: #2e3261;
    width: 100%;
    position: fixed;
   top: 0;

    height: 76px;
    overflow-x: hidden;
    position:fixed;
}
.navbar a {
    font-family: 'Open Sans', sans-serif;
    
    float: left;
    display: block;
    padding: 0px 5px 0 0;
    text-align: center;
    text-decoration: none;
    color:white;
    font-size: 15px;
}
ul{
    list-style-type: none;
    padding:0px 25px 0 25px;
    padding-left: 200px;
    display: flex;
     margin: auto;
}
li{
   
    padding:25px 0px  25px 0;
     margin: auto;
}
.navbar a:hover{
  border-block-start-width: 5px;
    border-bottom: 2px solid;
    border-bottom-color: #fe2a77;

}
.side-nav{
  height:0;
  width:100%;
  position:fixed;
  align-content: center;
  z-index:1;
  top:0;
  left:0;
  background-color: #2e3261;
  opacity:0.9;
  overflow-y:hidden;
  margin-top: 76px;
 
  transition:0.5s;
}
.side-nav a{
    align-content: center;
    display:block;
    font-family: 'Open Sans', sans-serif;
    text-decoration: none;
    text-align: center;
    color: white; 
    padding: 10px;
    
    }
    @media(max-width:900px){
  .navbar-nav{display:none}
  
  

@media(min-width:568px){
  .side-nav{display: none}
  .side-nav a{display: none}
  
}
}



</style>
