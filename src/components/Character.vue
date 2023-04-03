<template>
  <section>
    <div id="lignes" class="container-col">
      <div id="image" 
      v-bind:style="{ backgroundImage: 
      'url(' + character.thumbnail.path + '.' + character.thumbnail.extension + ')' }">
      </div>
      <div id="nom" class="container-row">
        <h1 @click="characterData=true">{{character.name}}</h1>
      </div>
    </div>

    <div class="modal-body" v-if="characterData" id="modal">
      <div class="container-fluid">
        
        <div class="row">
          <div class="col-md-12 sl-auto">{{character.description}}</div>
        </div>
        <div class="row">
          <div class="col-md-12 sl-auto">Comics : {{character.comics.available}}  </div>
        </div>

        <div class="row">
          <div class="col-md-12 sl-auto"> Series: {{character.series.available}}</div>
        </div>

        <div class="row">
          <div class="col-md-12 sl-auto"> Stories: {{character.stories.available}}</div>
        </div>

        <div class="row">
          <div class="col-md-12 sl-auto"> Events: {{character.events.available}}</div>
        </div>

        <div class="row">
         <div class="col-md-12 ml-auto" 
              v-for="serie in character.series.items.slice(0, 3)" :key="serie.name">{{serie.name}}</div>
        </div>
        
        <div class="col-md-6 ml-auto"></div>
        <div class="modal-footer">
          <button @click="characterData=false" type="button" class="btn btn-secondary" data-dismiss="modal">Cerrar</button>
        </div>      
      </div>
    </div>
  </section>
  
</template>

<script>
export default {
  name : "Character",
  props: {
    character: {
      type: Object,
    }
  },
  data() {
    return {
      characterData: false
    }
  }
}
</script>

<style>
.container-row {
  display : flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.container-col {
  display : flex;
  flex-direction: column;
  justify-content: space-between;
}

#lignes{
  width:254px;
  height:300px; 
  border-radius: 2%;
}

#lignes:hover{
    border: 2px solid #e92227;

}

#image {
  width: 250px;
  height: 250px;
  background-size: cover;
  border-radius: 2% 2% 0% 0%;
}

#nom {
  background-color:white;
  border: 1px solid rgba(180, 180, 180, 0.781);
  width: 250px;
  height: 80px;
  border-radius: 0% 0% 2% 2%;
}


h1{
  font-size: 20px;
  text-align: center;
  color:black;
}

h1:hover{
  font-size: 25px;
  color:#e92227;
}

#modalName{
  font-size: 25px;
  text-align: center;
  color:black;
}

#modal{
  width: 250px;
  background-color: white;
}

#characPic{
  width: 200px;
  height: 150px;
  background-size: cover;
}

</style>
