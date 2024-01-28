<script>

  import { Sidebar, SidebarGroup, SidebarItem, SidebarWrapper } from 'flowbite-svelte';
  import { GridSolid, TicketOutline, DollarOutline , ArrowRightFromBracketSolid, QuestionCircleOutline } from 'flowbite-svelte-icons';
  import '@fortawesome/fontawesome-free/css/all.min.css';
  import '@fortawesome/fontawesome-free/css/all.css';
  //import { writable } from 'svelte/store';
  //import { storeusername } from '../../store/store'/////////////////////
  
  let spanClass = 'flex-1 ms-3 whitespace-nowrap';
  let activeClass = 'flex items-center p-2 text-base font-normal text-primary-900 bg-primary-200 dark:bg-primary-700 rounded-lg dark:text-white hover:bg-primary-100 dark:hover:bg-gray-700';
  let nonActiveClass = 'flex items-center p-2 text-base font-normal text-green-900 bg-gray-200 rounded-lg dark:text-white hover:bg-green-100 dark:hover:bg-green-700';
  let activeUrl =  window.location.pathname + window.location.hash

  let username = '';

  //storeusername.subscribe( uname => { username = uname })/////////////////////

  username = window.localStorage.getItem("username")

  console.log(activeUrl,username)

  let homepath = "/#/home/" + username




</script>

<Sidebar {activeUrl} {activeClass} {nonActiveClass} {spanClass}>
  <SidebarWrapper class = "bg-gray-800 h-screen">
    <SidebarGroup>



      <SidebarItem label="Sort by earliest takeoff" href =  "{homepath}" >
        <svelte:fragment slot="icon">
            
            <i class="fa-solid fa-plane-departure"></i>

        </svelte:fragment> 
          
      </SidebarItem>

      


      <SidebarItem label="Sort by quickest flight">
        <svelte:fragment slot="icon">
            
            <i class="fa-solid fa-plane"></i>

        </svelte:fragment>
        
      </SidebarItem>
      
      <SidebarItem label= "Sort by pricing">
        <svelte:fragment slot="icon">
          <DollarOutline class="w-5 h-5 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" />
        </svelte:fragment>
      </SidebarItem>


  </SidebarGroup>
  <SidebarGroup border>

      <SidebarItem label="Hotel Booking" >
        <svelte:fragment slot="icon">
          
          <i class="fa-solid fa-hotel"></i>

          </svelte:fragment>
        <!-- <svelte:fragment slot="subtext">
          <span class="inline-flex justify-center items-center px-2 ms-3 text-sm font-medium text-gray-800 bg-gray-200 rounded-full dark:bg-gray-700 dark:text-gray-300" > Pro </span>
        </svelte:fragment> -->
      </SidebarItem>


      <SidebarItem label="Airplane" href="/#/airplane" >
        <svelte:fragment slot="icon">
            <i class="fa-solid fa-plane"></i>
        </svelte:fragment>
      </SidebarItem>


      <SidebarItem label="Bus" >
          <svelte:fragment slot="icon">

           <i class="fa-solid fa-bus"></i>
          
          </svelte:fragment>
      </SidebarItem>


      <SidebarItem label="Train" >

          
          <!-- <svelte:fragment slot="subtext">
            <span class="inline-flex justify-center items-center px-2 ms-3 text-sm font-medium text-gray-800 bg-gray-200 rounded-full dark:bg-gray-700 dark:text-gray-300" > Pro </span>
          </svelte:fragment> -->

      </SidebarItem>

      <SidebarItem label="Launch" >

          <svelte:fragment slot="icon">
            
            <i class="fa-solid fa-ship"></i>

            </svelte:fragment>
          <!-- <svelte:fragment slot="subtext">
            <span class="inline-flex justify-center items-center px-2 ms-3 text-sm font-medium text-gray-800 bg-gray-200 rounded-full dark:bg-gray-700 dark:text-gray-300" > Pro </span>
          </svelte:fragment> -->
          
      </SidebarItem>

  </SidebarGroup>
  <SidebarGroup border>


      

      <SidebarItem label="Help">
          <svelte:fragment slot="icon">
          <QuestionCircleOutline class="w-5 h-5 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" />
              
          </svelte:fragment>
      </SidebarItem>

      <SidebarItem label="Sign Out">
          <svelte:fragment slot="icon">
          <ArrowRightFromBracketSolid class="w-5 h-5 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" />
              
          </svelte:fragment>
      </SidebarItem>


    </SidebarGroup>
  </SidebarWrapper>
</Sidebar>

