<template>
    <div class="navbar">
    <div class="flex items-center">
        <button class="p-4 flex items-center justify-center">
            <a href="http://127.0.0.1:5173/"><img src="https://www.mojeek.com/logos/logo_cc.svg" width="165" height="50" alt="mojeek"></a>
        </button>
    </div>
    <div class="flex justify-end flex-1 px-2">
        <div class="flex items-stretch">
        <div v-for="(item, i) in tabItems" :key = "i" class="flex">
            <button class="flex items-center justify-center" @click="seletedTab = item.key; item.visited = true;" :class="`${seletedTab == item.key? 'text-base text-green' :item.visited? 'hover:underline text-base text-purple':'hover:underline text-base text-muted'}`">
                {{item.name}}<sup class="text-2xs text-muted italic antialiased font-serif">{{item.sup}}</sup>
            </button>
            <div v-if="i != tabItems.length - 1" class="divider divider-horizontal h-8 mt-2"></div>
            <div v-else class="mr-8"></div>
        </div>
        
        
        <div class="dropdown dropdown-end">
            <button tabindex="0" class="hover:bg-green rounded flex items-center justify-center mt-1">
                <span class="w-10 h-10 hover:text-white material-icons text-4xl text-muted">menu</span>
            </button>
            <ul tabindex="0" class="menu dropdown-content p-2 shadow bg-base-100 rounded-box w-80 mt-4">

            <div v-for="(item, i) in dropdownItems" :key = "i" @click="item.collapse=!item.collapse" class="collapse">
            <input type="checkbox" /> 
            <div class="flex items-center justify-between collapse-title">
                <p class="text-base text-muted">{{item.name}}</p>
                <span v-if=item.collapse class="material-icons text-muted">expand_less</span>
                <span v-else class="material-icons text-muted">expand_more</span>
            </div>
            <div class="collapse-content"> 
                <div v-for="(subItem, j) in item.collapseItems" :key = "j">
                <!--BUG HERE-->
                <button @click="subItem.visited=true; item.collapse=false" class="flex p-2">
                <span class="p-2 material-icons text-muted">{{subItem.svg}}</span>
                <p v-if=!subItem.visited class="text-blueLink px-3 py-2 hover:underline">{{subItem.name}}</p>
                <p v-else class="text-purple px-3 py-2 hover:underline">{{subItem.name}}</p>
                </button>
                </div>
            </div>
            </div>
            </ul>
        </div>
        </div>
    </div>
    </div>

    <!--
        <div class="px-4 py-1 mr-4 flex items-center justify-between">
        <div class="flex items-center">
            <button class="p-4 flex items-center justify-center">
                <a href="http://127.0.0.1:5173/"><img src="https://www.mojeek.com/logos/logo_cc.svg" width="165" height="50" alt="mojeek"></a>
            </button>
        </div>
        <div class="p-7 flex items-center">
            <button class="flex items-center justify-center" v-for="(item, i) in tabItems" :key = "i" @click="seletedTab = item.key; item.visited = true;" :class="`${seletedTab == item.key? 'text-base text-green' :item.visited? 'hover:underline text-base text-purple':'hover:underline text-base text-muted'}`">
                {{item.name}}<sup class="text-2xs text-muted italic antialiased font-serif">{{item.sup}}</sup>
                <div v-if="i != tabItems.length - 1" class="divider divider-horizontal h-8"></div>
                <div v-else class="mr-8"></div>
            </button>
            
            ---------
            <button class="flex items-center justify-center">
                    <p class="text-sm text-muted">Web</p>
            </button>
            <div class="divider divider-horizontal h-8 mt-1"></div>
            <button class="flex items-center justify-center">
                <p class="text-sm text-muted">Images</p>
            </button>
            <div class="divider divider-horizontal h-8 mt-1"></div>
            <button class="flex items-center justify-center">
                <p class="text-sm text-muted">News</p>
            </button>
            <div class="divider divider-horizontal h-8 mt-1"></div>
            <button class="relative flex items-center justify-center mr-10">
                <p class="text-sm text-muted">Emotions<sup class="ml-1 text-2xs text-muted italic antialiased font-serif">demo</sup></p>
            </button> 
            
            
            <button class="relative rounded-full hover:bg-light flex items-center justify-center p-3">
                <span class="material-icons text-3xl text-muted">textsms</span>
                <div class="rounded-full h-5 w-5 bg-primary text-white flex items-center justify-center absolute mb-5 ml-5">1</div>
            </button>
            ----------

            <div class="dropdown dropdown-end">
                <button tabindex="0" class="hover:bg-green rounded flex items-center justify-center mt-1">
                    <span class="w-10 h-10 hover:text-white material-icons text-4xl text-muted">menu</span>
                </button>
                <ul tabindex="0" class="dropdown-content menu p-2 shadow bg-base-100 rounded-box w-52">
                    <li><a>Item 1</a></li>
                    <li><a>Item 2</a></li>
                </ul>
            </div>
        </div>
    </div>
    -->
    
</template>

<script>
export default {
    data() {
        return {
            tabItems: [
                {name: 'Web', sup: '', key: 'web', visited: true},
                {name: 'Images', sup: '',key: 'images', visited: false},
                {name: 'News', sup: '', key: 'news', visited: false},
                {name: 'Emotions', sup: 'demo',key: 'emotions', visited: false},
            ],
            seletedTab: "web",
            dropdownItems: [
                // svg will be replaced with reak data in the actual implementation
                {name: 'Search', key: 'search', collapse: false, collapseItems:[
                    {name: 'Web', key: 'web', visited: false, svg: 'search'},
                    {name: 'Images', key: 'images', visited: false, svg:'camera'},
                    {name: 'News', key: 'news', visited: false, svg: 'feed'},
                ]},
                {name: 'Company', key: 'company', collapse: false, collapseItems:[]},
                {name: 'Products', key: 'products', collapse: false, collapseItems:[]},
                {name: 'Help & Support', key: 'help & support', collapse: false, collapseItems:[]},
                {name: 'Engage', key: 'engage', collapse: false, collapseItems:[]},
            ],
        }
    }
}
</script>

<!--
multi-level dropdown
<style>
.dropdown:hover > .dropdown-content {
	display: block;
}
</style>

<div class="dropdown inline-block relative">
	<button class="bg-gray-300 text-gray-700 font-semibold py-2 px-4 rounded inline-flex items-center">
		<span>Dropdown ?</span>
	</button>
	<ul class="dropdown-content absolute hidden text-gray-700 pt-1">
		<li><a class="rounded-t bg-gray-200 hover:bg-gray-400 py-2 px-4 block whitespace-no-wrap" href="#">Option 1</a></li>
		<li><a class="bg-gray-200 hover:bg-gray-400 py-2 px-4 block whitespace-no-wrap" href="#">Option 2</a></li>
      	<li class="dropdown">
          <a class="bg-gray-200 hover:bg-gray-400 py-2 px-4 block whitespace-no-wrap" href="#">Option 3 ?</a>
          	<ul class="dropdown-content absolute hidden text-gray-700 pl-5 ml-24 -mt-10">
          		<li><a class="bg-gray-200 hover:bg-gray-400 py-2 px-4 block whitespace-no-wrap" href="#">Option 3-1</a></li>
              	<li><a class="bg-gray-200 hover:bg-gray-400 py-2 px-4 block whitespace-no-wrap" href="#">Option 3-2</a></li>
            </ul>
      	</li>
		<li><a class="rounded-b bg-gray-200 hover:bg-gray-400 py-2 px-4 block whitespace-no-wrap" href="#">Option 4</a></li>
	</ul>
</div>
-->
