<template>
  <div class="q-pa-md" style="max-width: 300px">
    <div class="q-gutter-md">
      <q-badge color="secondary">Model: "{{ model }}"</q-badge>

      <q-select
        filled
        v-model="model"
        :options="options"
        stack-label
        label="Standard"
      >
        <div slot="selected">
          Company:
          <q-chip v-if="model" dense square color="white" text-color="primary" class="q-ma-none">
            <q-avatar color="primary" text-color="white" :icon="model.icon" />
            {{ model.label }}
          </q-chip>
          <q-badge v-else>*none*</q-badge>
        </div>
      </q-select>

      <q-select
        filled
        v-model="model"
        :options="options"
        stack-label
        label="Standard"
        color="secondary"
      >
        <q-chip
          slot="selected"
          slot-scope="scope"
          removable
          dense
          @remove="scope.removeAtIndex(scope.index)"
          :tabindex="scope.tabindex"
          color="white"
          text-color="secondary"
          class="q-ma-none"
        >
          <q-avatar color="secondary" text-color="white" :icon="scope.opt.icon" />
          {{ scope.opt.label }}
        </q-chip>
      </q-select>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      model: {
        label: 'Google',
        value: 'goog',
        icon: 'mail'
      },

      options: [
        {
          label: 'Google',
          value: 'goog',
          icon: 'mail'
        },
        {
          label: 'Facebook',
          value: 'fb',
          icon: 'bluetooth'
        },
        {
          label: 'Twitter',
          value: 'twt',
          icon: 'map'
        },
        {
          label: 'Apple',
          value: 'app',
          icon: 'golf_course'
        },
        {
          label: 'Oracle',
          value: 'ora',
          disable: true,
          icon: 'casino'
        }
      ]
    }
  }
}
</script>
