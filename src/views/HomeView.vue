<template>
  <div class="home">
    <Intro />
    <Services />
    <Clean />
    <List />
  </div>
</template>

<script>
// @ is an alias to /src
import Intro from "@/components/Intro";
import Services from "@/components/Services";
import Clean from "@/components/Clean";
import List from "@/components/List";

export default {
  name: "HomeView",
  components: {
    List,
    Clean,
    Services,
    Intro,
  },
};
</script>
