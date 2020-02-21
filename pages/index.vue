<template>
  <div id="outer">
    <div id="inner">
      <div id="more-inner" ></div>
    </div>
  </div>
</template>

<script>
import gql from 'graphql-tag'

export default {
  apollo: {
    hello: {
      skip: true,
      query: gql`query { hello { name } }`,
      error(err, vm) {
        console.log('BOOM!')
        console.log(err)
        vm.err = err
        // return true
      },
      errorPolicy: 'all'
    }
  }
}
</script>
