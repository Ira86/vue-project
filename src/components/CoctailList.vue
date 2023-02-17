<template>
<table class="table table-striped">
    <tr>
        <td>
              {{ props.row.strDrink }}
        </td>
        <td class="flex justify-left p-3">
          <t-button variant="secondary" @click="changeUrl(props.row.idDrink)">
            View
          </t-button>
        </td>
    </tr>

</table>
</template>

<script>
    
</script>