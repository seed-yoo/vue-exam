<template>

    <h1>{{ title }}</h1>
    <h2>{{ subTitle }}</h2>

    <table border="1">
        <thead>
            <tr>
                <th>순번</th>
                <th>번호</th>
                <th>이름</th>
                <th>핸드폰</th>
                <th>회사</th>
            </tr>
        </thead>
        <tbody>
            <tr v-bind:key="i" v-for="(personVo, i) in pList">
                <td>{{ i+1 }}</td>
                <td>{{ personVo.no }}</td>
                <td>{{ personVo.name }}</td>
                <td>{{ personVo.hp }}</td>
                <td>{{ personVo.company }}</td>
            </tr>
        </tbody>
    </table>
    
    <br><br>
    <button v-on:click="getList" type="button">데이터불러오기</button>

    <br><br>

    <span v-bind:key="i" v-for="(ageInfo, i) in radioAge">
        <label for="">{{ageInfo.text}}</label><input type="radio" name="age" v-bind:value="ageInfo.code" v-model="aPicked">
    </span>



    <p></p>

</template>
<script>

export default {
    name: "Ex08View",
    components: {},
    data() {
        return {
            title: "vue 공부시작",
            subTitle: "반복문",
            pList: [],
            aPicked: "30",
            radioAge: [ {text:"10대", code: "10"},
                        {text:"20대", code: "20"},
                        {text:"30대", code: "30"},
                        {text:"40대", code: "40"},
                        {text:"110대", code: "110"},
                        {text:"1000대", code: "1000"},
                        {text:"10000대", code: "10000"},
                        {text:"기타", code: "etc"}
                    ]
        };
    },
    methods: {
        getList(){
            console.log("데이터 수집중....");

            let personList = [
                {
                    no: 1, name: "정우성", hp: "010-1234-5678", company: "02-1212-7777"
                },
                {
                    no: 4, name: "이효리", hp: "010-2222-2222", company: "02-2121-3333"
                },
                {
                    no: 17, name: "유재석", hp: "010-9999-9999", company: "02-2222-8888"
                }
            ];
            this.pList = personList;
        }
    },
    created() {
        //this.getList();
    }
};
</script>
<style></style>