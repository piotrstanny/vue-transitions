<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1>Animations</h1>
                <hr>
                <h3>Fade effect:</h3>
                <button class="btn btn-primary" @click="showFirst = !showFirst">Show Alert</button>
                <transition name="fade">
                    <div class="alert alert-info" role="alert" v-if="showFirst">This is fading info alert!</div>
                </transition>
            </div>
        </div>
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-md-6">
                <hr>
                <h3>Slide effect:</h3>
                <button class="btn btn-warning" @click="showSecond = !showSecond">Toggle Alert</button>
                <transition name="slide">
                    <div class="alert alert-warning" role="alert" v-if="showSecond">This is sliding info alert!</div>
                </transition>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                showFirst: false,
                showSecond: false
            }
        }
    }
</script>

<style>
.container, .alert, hr {
    margin-top: 30px;
}
.row {
    height: 270px;
}
/* Fading transition */
.fade-enter {
    opacity: 0;
}
.fade-enter-active {
    transition: opacity .4s;
}
.fade-leave {

}
.fade-leave-active {
    transition: opacity 1s;
    opacity: 0;
}
.slide-enter {

}
/* Sliding animation */
.slide-enter-active {
    animation: slide-in 1s ease-out forwards;
}
.slide-leave {

}
.slide-leave-active {
    animation: slide-out 1s ease-in forwards;
}
@keyframes slide-in {
    from {
        transform: translateX(20px);
    }
    to {
        transform: translateX(0);
    }
}
@keyframes slide-out {
    from {
        transform: translateX(0);
    }
    to {
        transform: translateX(-800px);
    }
}
</style>
