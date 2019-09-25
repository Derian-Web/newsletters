<template>
  <div>
      <div class="card" style="width: 18rem;">
        <div style="width: 150px; position:relative;
    left:20px;" class="ml-5 mt-2">
          <img
            :src="image"
            class="card-img-top rounded-circle"
            alt
          />
        </div>
        <div class="card-body">
          <h5 class="card-title text-center">{{title}}</h5>
          <p class="card-text text-center">{{description}}</p>
          <div class="input-group mb-3">
            <div class="input-group-prepend">
              <span class="input-group-text" style="background:#fff;">
                <i class="fas fa-envelope" style="color:#FF8000;"></i>
              </span>
            </div>
            <input type="text" class="form-control" placeholder="Your email" />
          </div>
          <a
            href="#myModal"
            class="btn text-center"
            style="width: 100%; background:#FF8000; color:#fff;"
            data-toggle="modal"
          >Subscribete</a>
        </div>
      </div>
    <div class="modal fade" id="myModal">
    <div class="modal-dialog">
      <div class="modal-content">
      
        <!-- Modal Header -->
        <div class="modal-header">
          <div style="width: 150px; position:relative;
    left:100px;" class="ml-5 mt-2">
          <img
            :src="image"
            class="card-img-top rounded-circle"
            alt
          />
        </div>
          <button type="button" class="close" data-dismiss="modal">&times;</button>
        </div>
        
        <!-- Modal body -->
        <div class="modal-body">
          <h5 class="card-title text-center"></h5>
          <p class="card-text text-center"></p>
           <div class="input-group mb-3">
            <div class="input-group-prepend">
              <span class="input-group-text" style="background:#fff;">
                <i class="fas fa-envelope" style="color:#FF8000;"></i>
              </span>
            </div>
            <input type="text" class="form-control" placeholder="Your email" />
          </div>

        </div>
        
        <!-- Modal footer -->
        <div class="modal-footer">
          <a
            href="#myModal"
            class="btn text-center"
            style="width: 100%; background:#FF8000; color:#fff;"
            data-toggle="modal"
          >Subscribete</a>
        </div>
        
      </div>
    </div>
  </div>
  </div>
</template>
<script>
export default {
  props: ["title", "description", "image"]
}
</script>