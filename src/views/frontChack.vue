<script>
import { mapState, mapActions } from 'pinia'
import counter from '../stores/counter'
export default {
    data() {
    },
    computed: {
        ...mapState(counter, ["userData"])
    },
    methods: {
        inWeb() {

            let qDate = this.userData.qDate;
            let qTitle = this.userData.qTitle;
            let qText = this.userData.qText;
            let name = this.userData.name;
            let tel = this.userData.tel;
            let email = this.userData.email;
            let agee = parseInt(this.userData.age);
            let dataArr =[];

            let data = this.userData.value
            
            //每筆資料存進去就不會不見了
            if (JSON.parse(localStorage.getItem("data")) !== null) {
                dataArr = JSON.parse(localStorage.getItem("data"))
            } else {
                dataArr = [];
            }
            let dataObj = {
                // Data:this.userData,
                Date: qDate,
                Title: qTitle,
                Text: qText,
                personName: name,
                phone: tel,
                mail: email,
                age: agee,

            };
            // dataArr.push(dataObj)
            //將上述自訂的陣列dataObj推到最外面大的dataArr裡面
            dataArr.push(dataObj),
            //將dataArr放置在data裡面的json
            localStorage.setItem("data", JSON.stringify(dataArr))
        }
    }
}
</script>
<template>
    <div class="time">
        <p>問卷填寫時間</p>
        <span>{{ userData.qDate }}</span>
    </div>
    <div class="title">
        <p>問卷名稱</p>
        <span>{{ userData.qTitle }}</span>
    </div>
    <div class="produce">
        <p>問卷介紹</p>
        <span>{{ userData.qText }}</span>
    </div>
    <div class="content">
        <div class="information">
            <div class="one">
                <label>姓名：</label>
                <span>{{ userData.name }}</span>
            </div>
            <div class="two">
                <label>手機：</label>
                <span>{{ userData.tel }}</span>
            </div>
            <div class="three">
                <label>E-mail：</label>
                <span>{{ userData.email }}</span>
            </div>
            <div class="four">
                <label>年齡：</label>
                <span>{{ userData.age }}</span>
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
            <RouterLink :to="`/FrontInside`">修改</RouterLink>
        </button>
        <button type="submit" class="rounterItem" @click="inWeb">送出</button>
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
    border: 1px solid black
}

.produce {
    width: 80vw;
    height: 15vh;
    font-size: 28px;
    border: 1px solid black
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