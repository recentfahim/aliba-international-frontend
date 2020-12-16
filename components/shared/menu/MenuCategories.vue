<template lang="html">
    <ul class="menu--dropdown">
        <li v-for="(item, index) in menuCategories">
                    {{ item.Name }}
        </li>
    </ul>
</template>

<script>
import MenuDefault from '~/components/shared/menu/MenuDefault';
import MenuDropdown from '~/components/shared/menu/MenuDropdown';
import MenuMega from '~/components/shared/menu/MenuMega';
import axios from 'axios';
export default {
    name: 'MenuCategories',
    components: { MenuMega, MenuDropdown, MenuDefault },
    data() {
        return {
            menuCategories: []
        };
    },
  created() {
    axios.get(process.env.baseURL + `category`).then((response) => {
      this.menuCategories = response.data.data
    })
  }
};
</script>

<style lang="scss" scoped></style>
