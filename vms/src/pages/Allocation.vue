<template>
  <div class="py-12 h-full">
    <h2 class="font-bold text-lg text-gray-600 mb-4">
      Welcome to Allocation, {{ session.user }}!
    </h2>

    <div class="flex h-full">
      <div class="mt-2 flex-auto w-1/3">
        <Card title="KL 02 A 625" class="h-1/2">
          <div></div>
        </Card>

        <Card title="Allocation Summary" class="pt-2 h-1/2">
          <div></div>
        </Card>
      </div>

      <div class="mt-2 ml-2 flex-auto w-2/3">
        <Card title="Open Order" class="h-1/2">
          <ListView
            :columns="columns"
            :rows="rows"
            :options="{
              getRowRoute: (row) => ({
                name: 'Call Log',
                params: { callLogId: row.name },
              }),
              selectable: true,
              showTooltip: true,
              resizeColumn: true,
            }"
            row-key="name"
          >
          </ListView>
        </Card>

        <Card title="Allocated Order" class="pt-2 h-1/2">
          <div></div>
        </Card>
      </div>
    </div>

  </div>

</template>

<script setup>
import { ref } from 'vue';
import { session } from '../data/session';
import { ListView } from 'frappe-ui';

const columns = ref([
  {label: 'Name', key: 'name', width: 3,},
  {label: 'Email', key: 'email', width: '200px',},
  {label: 'Role', key: 'role',},
  {label: 'Status', key: 'status',},
])

const rows = ref([
  {
    id: 1,
    name: 'John Doe',
    email: 'john@doe.com',
    status: 'Active',
    role: 'Developer',
    user_image: 'https://avatars.githubusercontent.com/u/499550',
  },
  {
    id: 2,
    name: 'Jane Doe',
    email: 'jane@doe.com',
    status: 'Inactive',
    role: 'HR',
    user_image: 'https://avatars.githubusercontent.com/u/499120',
  },
])
</script>
