<template>
    <div> 
        <v-navigation-drawer expand-on-hover rail>
            <v-list>
                <v-list-item class="mb-2" prepend-avatar="https://www.nj.com/resizer/iqV2J-QFgh0227ybHBor4exTVBk=/800x0/smart/cloudfront-us-east-1.images.arcpublishing.com/advancelocal/SJGKVE5UNVESVCW7BBOHKQCZVE.jpg"  title="Sandra Adams"
            subtitle="sandra_a88@gmailcom"> 
                </v-list-item>
                <v-divider></v-divider> 
            </v-list>

            
            <v-list density="compact" nav>
                <v-list-item active prepend-icon="mdi-folder" title="My Files" value="myfiles"></v-list-item>
                <v-list-item prepend-icon="mdi-account-multiple" title="Shared with me" value="shared"></v-list-item>
            </v-list>
     
        </v-navigation-drawer>
    </div>
</template>