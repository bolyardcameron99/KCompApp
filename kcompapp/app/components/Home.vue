<template>
    <Page class="page">
        <ActionBar class="action-bar">
            <!-- 
            Use the NavigationButton as a side-drawer button in Android
            because ActionItems are shown on the right side of the ActionBar
            -->
            <NavigationButton ios:visibility="collapsed" icon="res://menu" @tap="onDrawerButtonTap"></NavigationButton>
            <!-- 
            Use the ActionItem for IOS with position set to left. Using the
            NavigationButton as a side-drawer button in iOS is not possible,
            because its function is to always navigate back in the application.
            -->
            <ActionItem icon="res://menu" 
                android:visibility="collapsed" 
                @tap="onDrawerButtonTap"
                ios.position="left">
            </ActionItem>
            <Label class="action-bar-title" text="Request Service"></Label>
        </ActionBar>

        <StackLayout class="page-content">
            <Label text="Date:" textWrap="true" verticalAlignment="center" horizontalAlignment="left"
            paddingTop="10" />
            <TextField hint="MM/DD/YYYY" verticalAlignment="center" horizontalAlignment="center" />
            <Label text="Location:" textWrap="true" verticalAlignment="center" horizontalAlignment="left" />
            <TextField hint="Enter Location.." verticalAlignment="center" horizontalAlignment="center" />
            <Label text="Caller:" textWrap="true" verticalAlignment="center" horizontalAlignment="left" />
            <TextField hint="Betty Smith" verticalAlignment="center" horizontalAlignment="center" />
            <Label text="Site Contact:" textWrap="true" verticalAlignment="center" horizontalAlignment="left" />
            <TextField hint="Jeff Lebowski" verticalAlignment="center" horizontalAlignment="center" />
            <Label text="Technician:" textWrap="true" verticalAlignment="center" horizontalAlignment="left" />
            <TextField hint="Bob Owens" verticalAlignment="center" horizontalAlignment="center" />
            <Label text="Status:" textWrap="true" verticalAlignment="center" horizontalAlignment="left" />
            <TextField hint="Enter Status.." verticalAlignment="center" horizontalAlignment="center" />
            
            <Label text="Trouble Reported" textWrap="true" verticalAlignment="center" horizontalAlignment="center"
            paddingTop="50" />
            

        </StackLayout>

        
        

    </Page>
</template>

<script>
    import * as utils from "~/shared/utils";
    import SelectedPageService from "../shared/selected-page-service";

    export default {
        mounted() {
            SelectedPageService.getInstance().updateSelectedPage("Home");
        },
        computed: {
            message() {
                return "<!-- Page content goes here ->";
            }
        },
        methods: {
            onDrawerButtonTap() {
                utils.showDrawer();
            }
        }
    };
</script>

<style scoped lang="scss">
    // Start custom common variables
    @import '~@nativescript/theme/scss/variables/blue';
    // End custom common variables

    // Custom styles
</style>
