<script>

  import { Sidebar, SidebarGroup, SidebarItem, SidebarWrapper, Input, Button, Label } from 'flowbite-svelte';
  import { GridSolid, TicketOutline, DollarOutline , ArrowRightFromBracketSolid, QuestionCircleOutline } from 'flowbite-svelte-icons';
  import '@fortawesome/fontawesome-free/css/all.min.css';
  import '@fortawesome/fontawesome-free/css/all.css';
  //import { writable } from 'svelte/store';
  //import { storeusername } from '../../store/store'/////////////////////
  
  // let spanClass = 'flex-1 ms-3 whitespace-nowrap';
  // let activeClass = 'flex items-center p-2 text-base font-normal text-primary-900 bg-primary-200 dark:bg-primary-700 rounded-lg dark:text-white hover:bg-primary-100 dark:hover:bg-gray-700';
  // let nonActiveClass = 'flex items-center p-2 text-base font-normal text-green-900 bg-gray-200 rounded-lg dark:text-white hover:bg-green-100 dark:hover:bg-green-700';
  // let activeUrl =  window.location.pathname + window.location.hash

  // let username = '';

  // //storeusername.subscribe( uname => { username = uname })/////////////////////

  // username = window.localStorage.getItem("username")

  // console.log(activeUrl,username)

  // let homepath = "/#/home/" + username

// {activeUrl} {activeClass} {nonActiveClass} {spanClass} href =  "{homepath}"

let upRange, lowRange

function handleClick(event) {

    event.preventDefault();
    
}

let timeRange = [0, 100];

let up = timeRange[1]

let warningMessage = '';

let air_line = []

import { storeAirline } from "../../store/store"

function filterMoney() {

  if (lowRange > upRange) {
    warningMessage = 'Lower value cannot be higher than the upper limit.';
  }

  else{

    storeAirline.set( air_line )
  }

}


</script>



<Sidebar >
  <SidebarWrapper class = "bg-gray-800 h-screen rounded-xl" >
    <SidebarGroup>



      <SidebarItem label="Set the upper price range" class = "text-gray-400" on:click =  { handleClick } >
        <svelte:fragment slot="icon">
            
        <DollarOutline class="w-5 h-5 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" />
        

        </svelte:fragment> 
          
      </SidebarItem>

      


      <SidebarItem label=""  on:click =  {handleClick}>
        <svelte:fragment slot="icon">
            
            <Input type= "number" id= "upper_lim" bind:value = {upRange} class= "w-full" ></Input>

        </svelte:fragment>
        
      </SidebarItem>
      
      <SidebarItem label= "Set the lower price range" class = "text-gray-400" on:click =  { handleClick }>
        <svelte:fragment slot="icon">
          <DollarOutline class="w-5 h-5 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" />
        </svelte:fragment>
      </SidebarItem>

      <SidebarItem label="" on:click =  {handleClick}>

        <svelte:fragment slot="icon"  >
            
            <Input type= "number" id= "lower_lim" bind:value = { lowRange } class= "w-full" ></Input>

        </svelte:fragment>
        
      </SidebarItem>

      <SidebarItem label="" on:click =  {handleClick}>

        <svelte:fragment slot="icon"  >
            
          <Button shadow color="blue" class = "w-full" on:click = {() => filterMoney()}> search </Button>

        </svelte:fragment>
        
      </SidebarItem>


  </SidebarGroup>
  <SidebarGroup border>

      <SidebarItem label="Time Range: {timeRange[0]} - {timeRange[1]} hours" for="time-slider" class = "text-gray-400" on:click =  {handleClick}>

       
      </SidebarItem>


      <SidebarItem label="" on:click =  {handleClick} >
        <svelte:fragment slot="icon">

        <input type="range" id="time-slider" class = "w-full" min={timeRange[0]} max={up} step="1" bind:value={timeRange[1]} />

        </svelte:fragment>
      </SidebarItem>


      <SidebarItem label="" on:click =  {handleClick}>

        <svelte:fragment slot="icon"  >
            
          <Button shadow color="blue" class = "w-full" > search </Button>

        </svelte:fragment>
        
      </SidebarItem>


      
      

  </SidebarGroup>
  
  </SidebarWrapper>
</Sidebar>



