<template>
  <b-modal
    id="testing"
    :title="$t('guildReminderTitle')"
    size="lg"
    :hide-footer="true"
  >
    <div class="modal-body text-center">
      <br>
      <div class="scene_guilds"></div>
      <br>
      <h4>{{ $t('guildReminderText1') }}</h4>
    </div>
    <div class="modal-footer">
      <div class="container-fluid">
        <div class="row">
          <div class="col-6 text-center">
            <button
              class="btn btn-secondary"
              @click="close()"
            >
              {{ $t('guildReminderDismiss') }}
            </button>
          </div>
          <div
            class="col-6 text-center"
            @click="close()"
          >
            <div
              class="btn btn-primary"
              @click="takeMethere()"
            >
              {{ $t('guildReminderCTA') }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </b-modal>
</template>

<style scoped>
  .scene_guilds {
    margin: 0 auto;
  }
</style>

<script>
export default {
  methods: {
    close () {
      this.$root.$emit('bv::hide::modal', 'testing');
    },
    takeMethere () {
      this.$router.push('/groups/discovery');
      this.close();
    },
  },
};
</script>
