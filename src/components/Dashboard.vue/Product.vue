<template>
  <div class="modal fade" id="ModalAdd" tabindex="-1" role="dialog">
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title">Add Item</h5>
          <button type="button" class="close" data-dismiss="modal" aria-label="Close">
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <div class="modal-body">
          <div class="name row mb-2">
            <div class="col-3 pt-1">Name</div>
            <div class="col-9" style="border: none;">
              <input
                type="text"
                class="form-control shadow-sm bg-white rounded"
                aria-label="Sizing example input"
                aria-describedby="inputGroup-sizing-default"
              />
            </div>
          </div>
          <div class="name row mb-2">
            <div class="col-3 pt-1">Image</div>
            <div class="col-9" style="border: none;">
              <input
                type="text"
                class="form-control shadow-sm bg-white rounded"
                aria-label="Sizing example input"
                aria-describedby="inputGroup-sizing-default"
              />
            </div>
          </div>
          <div class="name row mb-2">
            <div class="col-3 pt-1">Price</div>
            <div class="col-5" style="border: none;">
              <input
                type="text"
                class="form-control shadow-sm bg-white rounded"
                aria-label="Sizing example input"
                aria-describedby="inputGroup-sizing-default"
              />
            </div>
          </div>
          <div class="name row mb-2">
            <div class="col-3 pt-1">Category</div>
            <div class="col-5" style="border: none;">
              <div class="dropdown">
                <button
                  class="btn btn-secondary dropdown-toggle"
                  style="background-color: white; color: #CECECE;"
                  type="button"
                  id="dropdownMenuButton"
                  data-toggle="dropdown"
                  aria-haspopup="true"
                  aria-expanded="false"
                >Category</button>
                <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
                  <a class="dropdown-item" href="#">Action</a>
                  <a class="dropdown-item" href="#">Another action</a>
                  <a class="dropdown-item" href="#">Something else here</a>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-primary" data-dismiss="modal">Close</button>
          <button type="button" class="btn btn-danger">Add</button>
        </div>
      </div>
    </div>
  </div>
</template>
