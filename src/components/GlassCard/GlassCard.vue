<template>
    <a :href="'/blog/'+card_config.BlogID" class="card">
      <h1 :class="card_config.Color" v-html="card_config.Tag"></h1>
      <h2 :class="card_config.Color">{{ card_config.Desc }}</h2>
      <span :class="card_config.Color"></span>
      <div class="glass">
        <h2>{{ card_config.Author }}<br><i>{{ card_config.Title }}</i></h2>
      </div>
    </a>
</template>

<script>
export default {
  props: {
    card_config: Object,
  },
}
</script>

<style scoped>
.blue{
  color: #01b2fe;
}
span.blue{
  background: #01b2fe;
}
.red{
  color: #ff008c;
}
span.red{
  background: #ff008c;
}
.yellow{
  color: #ffcd00;
}
span.yellow{
  background: #ffcd00;
}
.green{
  color: #00c456;
}
span.green{
  background: #00c456;
}
.purple{
  color: #6c5ce7;
}
span.purple{
  background: #6c5ce7;
}
.orange{
  color: #d63031
}
span.orange{
  background: #d63031
}

.card{
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 350px;
}

.card>h1{
  font-family: "Calibri Light", sans-serif;
  font-size: 5em;
  font-weight: 800;
  max-width: 300px;
  max-height: 200px;
  overflow: hidden;
  word-break: break-all;
  position: absolute;
  filter: blur(3px);
  transition: all 0.5s ease-in-out;
}

.card:hover>h1{
  transform: translateY(-20px);
  opacity: 0;
}

.card>h2{
  font-family: "Calibri Light", sans-serif;
  position: absolute;
  filter: blur(5px);
  opacity: 0;
  max-width: 300px;
  max-height: 200px;
  overflow: hidden;
  word-break: break-all;
  text-decoration: none;
  transition: all 0.5s ease-in-out;
}

.card:hover>h2{
  transform: translateY(-20px);
  filter: blur(0);
  opacity: 1;
}

.card span{
  width: 350px;
  height: 200px;
  display: block;
  filter: blur(90px);
  opacity: 0.9;
  transition: all 0.5s ease-in-out;
  overflow: hidden;
}

.card:hover span{
  transform: translateY(-20px);
}

.card .glass{
  position: absolute;
  width: 350px;
  height: 250px;
  background: rgba(255, 255, 255, 0.5);
  border-radius: 20px;
  border: 1px solid #fff;
  overflow: hidden;
  display: flex;
  justify-content: flex-start;
  align-items: flex-end;
  transition: all 0.5s ease-in-out;
}

.card .glass:hover{
  transform: translateY(-20px);
  background: rgba(255, 255, 255, 0.2);
}

.card .glass::before{
  content: '';
  position: absolute;
  top: 0;
  left: -50%;
  width: 100%;
  height: 100%;
  background: rgba(255, 255, 255, 0.2);
  pointer-events: none;
  transform: skewX(345deg);
  transition: all 0.5s ease-in-out;
}

.card .glass:hover::before{
  transform: skewX(345deg) translateX(-300px);
}

.card .glass::after{
  content: '';
  position: absolute;
  top: 0;
  right: -50%;
  width: 100%;
  height: 100%;
  background: rgba(255, 255, 255, 0.3);
  pointer-events: none;
  transform: skewX(345deg) translateX(300px);
  transition: all 0.5s ease-in-out;
}

.card .glass:hover::after{
  transform: skewX(345deg) translateX(0);
}

.card .glass h2{
  padding: 20px;
  font-weight: 400;
  width: 100%;
  background: rgba(255, 255, 255, 0.2);
  color: #333;
  text-align: end;
  transition: all 0.5s ease-in-out;
}

.card:hover .glass h2{
  background: rgba(255, 255, 255, 0);
  opacity: 0;
}

.card .glass h2 i{
  font-weight: 300;
  font-size: 0.75em;
  font-style: normal;
}
</style>