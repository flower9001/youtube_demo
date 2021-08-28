<template lang='pug'>
    header.container
        .row.justify-content-center.align-item-center
            .col.me-auto
                a.text-content( href="#" )
                    i.fab.fa-youtube.fa-lg
                    span.logo YouTube
            .col-1
                a( href="#" )
                    i.fas.fa-search.fa-lg
            .col-1
                img.rounded-circle.user( src="@/assets/images/user_img.jpg" )/

</template>

<style lang="scss">
    .container {
        font-family: Roboto, Arial, sans-serif;
    }
    .user{
        height: 32px;
        width: 32px;
    }
    .fa-youtube{
        height: 20px;
        width: 30px;
        color: red;
    }
    a {
        text-decoration: none;
    }
    .logo {
        color: #000;
        font-weight: 800;
    }
    header {
        .row {
            height: 56px;
        }        
    }
    .fa-search {
        color: gray;
    }
</style>