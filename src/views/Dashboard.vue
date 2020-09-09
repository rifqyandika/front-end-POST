<template>
  <div>
    <Navbar />
    <div class="container-fluid">
      <center>
        <div class="row p-5">
        <div class="col-md-4">
          <div class="card status1 text-dark mb-3 shadow" style="max-width: 25rem; height: 12rem;">
              <div class="card-body text-left mt-4">
                <h5 class="card-title">Primary card title</h5>
                <p
                  class="card-text"
                >Some quick example text to build on the card title and make up the bulk of the card's content.</p>
              </div>
            </div>
        </div>
        <div class="col-md-4">
          <div class="card status2 text-dark mb-3 shadow" style="max-width: 25rem; height: 12rem;">
              <div class="card-body text-left mt-4">
                <h5 class="card-title">Primary card title</h5>
                <p
                  class="card-text"
                >Some quick example text to build on the card title and make up the bulk of the card's content.</p>
              </div>
            </div>
        </div>
        <div class="col-md-4">
          <div class="card status3 text-dark mb-3 shadow" style="max-width: 25rem; height: 12rem;">
              <div class="card-body text-left mt-4">
                <h5 class="card-title">Primary card title</h5>
                <p
                  class="card-text"
                >Some quick example text to build on the card title and make up the bulk of the card's content.</p>
              </div>
            </div>
        </div>
      </div>
      </center>
    </div>
  </div>
</template>

<script>
import Navbar from '../components/Navbar'

export default {
  components: {
    Navbar
  }
}
</script>
<style scoped>
.status1 {
  background: linear-gradient(278.29deg, #FBB2B4 30.05%, rgba(255, 143, 178, 0) 133.19%);
  border-radius: 10px;
}

.status2 {
  background: linear-gradient(278.29deg, #29DFFF 30.05%, rgba(41, 223, 255, 0) 133.19%);
  border-radius: 10px;
}

.status3 {
  background: linear-gradient(278.29deg, #AB84C8 30.05%, rgba(241, 201, 236, 0) 133.19%);
  border-radius: 10px;
}
</style>
