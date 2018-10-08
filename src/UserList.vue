<template>
  <div class="user-list">
    <table class="" style="padding-top: 5px">
      <tbody>
        <tr v-for="user in participants" :key="user.id">
            <td v-if="user.avatarHtml" class="avatar">
              <span class="avatar-html" v-html="user.avatarHtml"></span>
            </td>
            <td v-else style="text-align: center;"><img :src="user.imageUrl" class="img-msg"/></td>
            <td>{{user.name}}</td>
        </tr>
      </tbody>
  </table>
  </div>
</template>
<script>
export default {
  props: {
    participants: {
      type: Array,
      required: true
    }
  }
}
</script>
<style scoped>
  .user-list {
    height: 100%;
    overflow: auto;
    padding-left: 5px;
    padding-top: 8px;
  }
  .img-msg {
    border-radius: 50%;
    width: 50px;
    margin-right: 5px;
  }
  table {
    width: 100%;
  }
  td.avatar{
    padding-left: 20px;
    width: 20%;
  }
  td{
    text-align: left;
    vertical-align: middle;
  }
</style>
