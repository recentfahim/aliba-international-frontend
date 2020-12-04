<template>
    <v-row>
        <v-col md="4">
            <TopRankingProductContainer :title="title1"></TopRankingProductContainer>
        </v-col>
        <v-col md="4">
            <TopRankingProductContainer :title="title2"></TopRankingProductContainer>
        </v-col>
        <v-col md="4">
            <TopRankingProductContainer :title="title3"></TopRankingProductContainer>
        </v-col>
    </v-row>
</template>

<script>
import TopRankingProductContainer from '~/components/product/TopRankingProductContainer';

export default {
    name: "TopRankingProductContainerList",
    components: {
        TopRankingProductContainer
    },
    data() {
        return {
            title1: 'Head Phones',
            title2: 'Ear Phones',
            title3: 'Dust Proof'
        }
    }
}
</script>

<style scoped>
.ranking-list{
    background-color: rgba(0,0,0,.04);
    border-radius: 5px;
}
.ranking-item-title{
    text-align: left;
    font-size: 13px;
    color: #000;
    line-height: 18px;
    height: 18px;
    font-weight: 700;
    margin-bottom: 4px;
    width: 254px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
}
.ranking-item{
    padding-left: 12px;
}
.ranking-item-sold-count{
    text-align: left;
    line-height: 13px;
    font-size: 11px;
    color: #999;
    height: 13px;
    margin-bottom: 8px;
    display: inline-block;
}

.ranking-item-badge {
    float: right;
    background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAABACAMAAABMUIWcAAAAkFBMVEUAAAD138v/5djy28L14Mr/6cv049Dy2sL04cv148/y2sHx28L04tDx28Ly28H048/y28L148/149Dy3ML14tDz28L148/z4Mr24cv228j249D55ND////148/149Dy28H149Dy2sL148/048/049Dy2sP15M/x28Lz4Mf55tL04s/x2sHy3MXz3sf04c304Mo+YFUfAAAAKnRSTlMANgmqWBHt7XX7+/Tv79nYt7WsiYVmZV5GHBsTBPXz4+LIxaWkmJVxKShTprfnAAABEklEQVRIx4XV2W7CMBCF4clCCKVlaYFSoPueYyfv/3ZdcBJbXs5/F+mT7ZFGipgmu/XyoQkk524r8x0BddMkQdYQcM3AJQHHhoCcAH4Ff2TJQF4RIBsGDjMC5I2BjAF5YaBk4PREgNQMTO4JkA8GvhmQNQN7BmTJwI6BvCJANgwcZgTIKwMZBS0BhUqDuwu0SXAD6BTIpwBSYIvfdAIs/oCKgz3+66JgdQYqBr5gaiPgvQcqsvZz9IVBjSEdAqdHjIVACasuAJ5toHyQwan1QAFEjhgWIXZEvwgmf9JxEdxcUMJLO6DwgXLAFfw6C+QIpCxwRKiWXAEdf6TJAlkQ6BHIZ1A4P/dpbNJhJberxTw06Q8ZdfzFmcjJiQAAAABJRU5ErkJggg==) 0 0 no-repeat;
    padding-left: 10px;
    background-size: contain;
}
.ranking-item-badge-text{
    background: #f4e2cf;
    color: #c7864d;
    text-align: right;
    line-height: 19px;
    font-weight: 700;
    padding: 0 10px 0 0;
    height: 20px;
    display: inline-block;
}
</style>