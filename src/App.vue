<script setup>
const days = ['пн', 'вт', 'ср', 'чт', 'пт', 'сб', 'вс'];
</script>

<template>
    <div class="center container">
        <div class="names-header">Artabas & Karina</div>

        <div class="text-header">Август 2023</div>
        <div class="calendar">
            <table>
                <tbody>
                <tr style="text-transform: uppercase;">
                    <td v-for="day in days" style="padding-bottom: 10px">{{ day }}</td>
                </tr>
                <tr>
                    <td></td>
                    <td v-for="i in 6">{{ i }}</td>
                </tr>
                <tr>
                    <td v-for="i in 7">{{ i + 6 }}</td>
                </tr>
                <tr>
                    <td v-for="i in 7" :class="{'target': i === 7}">
                        <span>{{ i + 13 }}</span>
                        <img src="./assets/icons/heart.svg" alt="" v-if="i === 7" width="58">
                    </td>
                </tr>
                <tr>
                    <td v-for="i in 7">{{ i + 20 }}</td>
                </tr>
                <tr>
                    <td v-for="i in 4">{{ i + 27 }}</td>
                </tr>
                </tbody>
            </table>
            <img src="./assets/icons/t.png" alt="" width="70" class="heart">
        </div>
        <div class="text-header" style="margin-top: 20px">Пора веселиться</div>
        <div class="text-subheader">Приглашаем Вас на нашу свадебную<br> вечеринку</div>
    </div>


    <div
        style="position: absolute; bottom: 30px; left:0;display: flex; flex-direction: column; align-items: center; width: 100%">
        <div class="text-header" style="margin-top: 10px; font-size: 20px;">
            <div>АВГУСТ 20, 2023</div>
            <div style="position: relative">
                <div>15:00</div>
                <img src="./assets/icons/lines.svg" alt="" width="100"
                     style="position: absolute; bottom: -15px; left: 15%; transform: rotate(8deg)">
            </div>
        </div>
        <div class="text-subheader" style="margin-top: 20px">ждем вас по адресу</div>
        <div class="text-subheader" style="font-size: 18px;position: relative">
            <span>
                Чемальский тракт 4 км, 1 <br>Чемальский район
            </span>
            <img src="./assets/icons/location.svg" alt="" width="16" style="position: absolute; top: 0; left: -22px;">
        </div>
    </div>

    <div style="position: absolute; top: 0; left: 0; overflow: hidden; min-height: 100vh; width: 100%; z-index: 2">
        <img src="./assets/icons/first.svg" alt="" class="first-flower flower" width="200">
        <img src="./assets/icons/first.svg" alt="" class="second-flower flower" width="200">
    </div>
</template>

<style scoped>
.names-header {
    font-family: Amsterdam, cursive;
    color: #C99071;
    font-size: 40px;
    margin-top: 2rem;
}

.center {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.calendar, .text-header, .text-subheader {
    font-family: Fors, serif;
}

.calendar {
    margin-top: 10px;
    text-align: center;
    position: relative;
}

.calendar .heart {
    position: absolute;
    bottom: -30px;
    right: -35px;
}

.calendar table td {
    padding-right: 10px;
    padding-left: 10px;
    padding-top: 10px;
}

.calendar table {
    font-size: 14px;
}

.calendar tr {
    margin-top: 3px;
}

.target {
    position: relative;
}

.target img {
    position: absolute;
    top: -5px;
    left: -8px;
    transform: rotate(30deg);
}

.text-header {
    font-size: 22px;
    text-transform: uppercase;
}

.text-header, .text-subheader {
    color: #545454;
    text-align: center;
}

.flower {
    position: absolute;
}

.first-flower {
    left: -76px;
    bottom: 0;
    transform: rotate(30deg);
}

.second-flower {
    right: -150px;
    top: 20%;
    transform: rotate(30deg);
}
</style>
