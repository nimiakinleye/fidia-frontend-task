<template>
  <div>
    <allNav />
    <div class="grid grid-cols-12">
      <div class="my_container">
        <page-header />
        <div class="payments_tabs">
          <h5>All</h5>
          <h5 class="active">Succeded</h5>
          <h5>Refunded</h5>
          <h5>Uncaptured</h5>
        </div>
        <table class="table">
          <thead>
            <tr>
              <th class="">Amount</th>
              <th class=""></th>
              <th class="w-4/6">Description</th>
              <th class="w-3/12">Customer</th>
              <th class="w-3/12">Date</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(customer, i) in succeded" :key="i">
              <td>US{{ customer.amount }}</td>
              <td class="succeded" v-if="customer.status">
                <div>
                  <p>Succeded</p>
                  <svg
                    width="16"
                    height="16"
                    viewBox="0 0 16 16"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M5.97274 11.9097L2.21974 8.19125C1.92724 7.89575 1.92724 7.4165 2.21974 7.12175C2.51224 6.827 2.98774 6.82625 3.28024 7.12175L6.50074 10.2897L12.7167 4.09625C13.0092 3.8015 13.4847 3.8015 13.7772 4.09625C14.0697 4.391 14.0697 4.871 13.7772 5.16575L7.02499 11.906C6.88579 12.0455 6.69705 12.1241 6.50001 12.1248C6.30298 12.1255 6.11368 12.0482 5.97349 11.9097H5.97274Z"
                      fill="#0E6245"
                    />
                  </svg>
                </div>
              </td>
              <td class="rejected" v-else>
                <div>
                  <p>Rejected</p>
                  <svg
                    width="16"
                    height="16"
                    viewBox="0 0 24 25"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M18 6.5L6 18.5"
                      stroke="#BF3333"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    />
                    <path
                      d="M6 6.5L18 18.5"
                      stroke="#BF3333"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    />
                  </svg>
                </div>
              </td>
              <td>{{ customer.description }}</td>
              <td>{{ customer.customer }}</td>
              <td>{{ customer.date }}</td>
              <td>...</td>
            </tr>
          </tbody>
        </table>
        <div class="payments_footer">
          <p>{{ succededLength }} Results</p>
          <div>
            <button class="previous">Previous</button>
            <button class="next">Next</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import allNav from '~/components/allNav.vue'
import pageHeader from '~/components/pageHeader.vue'
export default {
  data() {
    return {
      succeded: [
        {
          amount: '$352.22',
          status: true,
          description: 'fe3d8216-58f9-4dc1-aaef-2f19463b5258',
          customer: 'hefovo87@ereyemind...',
          date: '7 Jul, 14:04',
        },
        {
          amount: '$39.99',
          status: true,
          description: '0d7b6ac7-dbda-4157-bae9-e64749e538f5',
          customer: 'john.doe@gmail.com',
          date: '7 Jul, 14:01',
        },
        {
          amount: '$19.99',
          status: true,
          description: 'eca84b25-0324-4f31-b9fb-d489048b77ae',
          customer: 'jfamosinhoaraca@iseo...',
          date: '7 Jul, 13:28',
        },
        {
          amount: '$19.99',
          status: true,
          description: '9ce0027a-2429-40aa-bca3-eb9fae9829db',
          customer: 'gdontdisable@typery...',
          date: '7 Jul, 13:02',
        },
        {
          amount: '$142.17',
          status: true,
          description: '73bb0713-d326-4983-a805-9cef0f15ff3c',
          customer: 'psir@typre.com',
          date: '7 Jul, 12:34',
        },
        {
          amount: '$93.76',
          status: true,
          description: 'dff08e3b-037e-4fc9-a587-92850d82868e',
          customer: 'qomarkhalildubai0@g...',
          date: '7 Jul, 12:16',
        },
        {
          amount: '$931.00',
          status: true,
          description: '3005be4a-6d4d-487c-85c3-d61cfe64ef63',
          customer: 'kfouzan.saleemc@yah...',
          date: '7 Jul, 11:31',
        },
        {
          amount: '$19.99',
          status: true,
          description: '7e960154-e2e2-49eb-9252-edd51f421cd0',
          customer: 'asaifah@gmx.com',
          date: '7 Jul, 11:18',
        },
        {
          amount: '$41.99',
          status: true,
          description: '88f37e63-c2b2-4c09-aa89-428fc802fe09',
          customer: '5mohamad.hamod.5m...',
          date: '7 Jul, 10:46',
        },
        {
          amount: '$179.98',
          status: true,
          description: '5a9aae47-1d6a-484e-8305-c75107796cd1',
          customer: '7lucyveenstra918@g...',
          date: '7 Jul, 10:12',
        },
        {
          amount: '$15.17',
          status: true,
          description: '48eb8b41-9ff0-4d5d-82cc-4b9b820b5f53',
          customer: '0sajad@yopmail.com',
          date: '7 Jul, 06:03',
        },
        {
          amount: '$41.99',
          status: true,
          description: '02fd1b96-0bba-48aa-8557-81021755b196',
          customer: 'feverton78@gmail.com',
          date: '6 Jul, 23:45',
        },
        {
          amount: '$67.83',
          status: true,
          description: '986bdfca-6c8d-4f40-b2ae-ed0abacccfce',
          customer: 'lsid.ali_blidi@outlook...',
          date: '6 Jul, 23:32',
        },
        {
          amount: '$35.01',
          status: true,
          description: 'c5629140-ea34-40d8-97e4-d2986b33275e',
          customer: 'twendel.b@yahoo.com',
          date: '6 Jul, 23:30',
        },
        {
          amount: '$374.93',
          status: true,
          description: 'c2194818-1485-437c-a389-6164e605d697',
          customer: 'pdevonneq@gmail.com',
          date: '6 Jul, 23:16',
        },
        {
          amount: '$330.91',
          status: true,
          description: '6583691d-4d9f-43ce-8f2f-0d2d95b30ad4',
          customer: 'atotspop886@gmx.com',
          date: '6 Jul, 23:08',
        },
      ],
    }
  },
  computed: {
    succededLength() {
      return this.succeded.length
    },
  },
  components: {
    allNav,
    pageHeader,
  },
}
</script>

<style>
.payments_tabs {
  @apply flex
  border-b
  border-gray-300
  py-2
  sticky
  top-28
  bg-white
  z-0;
}

.payments_tabs h5 {
  @apply mr-5
  pb-2;
}

.payments_tabs h5.active {
  @apply border-b-2
  border-purple-700
}

.table {
  @apply table-fixed
  mt-5;
}

table th {
  @apply mx-4
  text-left;
}

tbody tr td {
  @apply py-1
  border-b
  border-t
  border-gray-300;
}

.succeded,
.rejected {
  @apply font-semibold
  p-2;
}

.succeded div,
.rejected div {
  @apply flex
  items-center;
}

.succeded div {
  @apply bg-green-200
  text-green-800
  px-2
  rounded-md;
}

.rejected div {
  @apply bg-red-200
  text-red-800
  px-2
  rounded-md;
}

.payments_footer {
  @apply flex
  items-center
  justify-between
  my-3;
}

.payments_footer button {
  @apply p-1.5
  px-3
  shadow
  ml-2;
}

.payments_footer .previous {
  @apply opacity-60;
}

.payments_footer .next {
  @apply bg-gray-50;
}
</style>