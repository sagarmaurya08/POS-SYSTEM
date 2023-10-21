<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
    <div>
        <section class="content-header">
            <div class="container-fluid">
                <div class="row mb-2">
                    <div class="col-sm-6">
                        <h1>{{ msg }}</h1>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>