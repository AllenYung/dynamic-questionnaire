<script>
import check from '../views/frontChack.vue'
import { computed } from "vue";
import { ref, provide } from "vue";
import { mapState, mapActions } from 'pinia'
import counter from '../stores/counter'
export default {
    data() {
        return {
        }
    },
    methods: {
        ...mapActions(counter, ["setData"]),
    },
    components: {
        check,
    },
    // provide() {
    //     return {
    //         nameIn: computed(() => this.name),
    //         telIn: computed(() => this.tel),
    //         emailIn: computed(() => this.email),
    //         ageIn: computed(() => this.age),
    //     }
    // },
    computed: {
        ...mapState(counter, ["userData"]),
    },
}
</script>
<template>
    <div class="time">
        <p>問卷填寫時間</p>
        <input type="time" v-model="this.userData.qDate">

    </div>
    <div class="title">
        <p>問卷名稱</p>
        <input type="text" class="titleIn" v-model="this.userData.qTitle" >
    </div>
    <div class="produce">
        <p>問卷介紹</p>
        <textarea name="" id="" cols="30" rows="10" v-model="this.userData.qText"></textarea>
    </div>
    <div class="content">
        <div class="information">
            <div class="one">
                <label>姓名：</label>
                <input type="text" name="name" id="name" v-model="this.userData.name">
            </div>
            <div class="two">
                <label>手機：</label>
                <input type="tel" name="tel" id="tel" v-model="this.userData.tel">
            </div>
            <div class="three">
                <label>E-mail：</label>
                <input type="emil" name="email" id="email" v-model="this.userData.email">
            </div>
            <div class="four">
                <label>年齡：</label>
                <input type="number" name="age" id="age" v-model="this.userData.age">
            </div>
        </div>
        <div class="question">
            <div class="one"></div>
            <div class="two"></div>
            <div class="three"></div>
        </div>
    </div>
    <div class="footer">
        <button type="submit" class="rounterItem">
            <RouterLink :to="`/Front`">取消</RouterLink>
        </button>
        <button type="submit" class="rounterItem" @click="">
            <RouterLink :to="`/FrontChack`">送出</RouterLink>
        </button>
    </div>
</template>

<style scoped lang="scss">
.time {
    width: 30vw;
    height: 7vh;
    margin-left: 40%;
    margin-top: 3%;
    font-size: 16px;
    border: 1px solid black;
}

.title {
    width: 80vw;
    height: 10vh;
    font-size: 28px;
    border: 1px solid black;

    .titleIn {
        width: 50vw;
        height: 5vh;
        font-size: 20px;
    }
}

.produce {
    width: 80vw;
    height: 15vh;
    font-size: 28px;
    border: 1px solid black
}

textarea {
    width: 80%;
    height: 10vh;
}


.content {
    display: flex;
    justify-content: center;

    .information {
        width: 800px;
        height: 300px;
        border: 1px solid black;
        font-size: large;
        position: relative;

        span {
            width: 70px;
            position: absolute;
            left: 50px;
        }

        input {
            position: absolute;
            width: 500px;
            height: 25px;
            left: 200px;
        }

        .one {
            position: absolute;
            top: 20px;
        }

        .two {
            position: absolute;
            top: 80px;
        }

        .three {
            position: absolute;
            top: 140px;
        }

        .four {
            position: absolute;
            top: 200px;
        }
    }
}

.footer {
    .rounterItem {
        margin-left: 10px;
        text-decoration: none;
    }
}
</style>