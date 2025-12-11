<script lang="ts">
  import { Template } from "@nativescript-community/svelte-native/components";
  import { customizeTabs } from './tab-customize';

  const items: { title: string }[] = [];
  for (let i = 0; i < 100; i++) {
    items.push({
      title: `Item ${i + 1}`,
    });
  }
</script>

<page statusBarStyle="light" class="bg-black">
  <tabView
    iosTabBarMinimizeBehavior="onScrollDown"
    tabTextFontSize="11"
    selectedTabTextColor="#fff"
    on:loaded={customizeTabs}
    class="bg-black"
  >
    <tabViewItem title="Home" iconSource="sys://house.fill">
      <listView {items} separatorColor="transparent" class="bg-black">
        <Template let:item>
          <gridLayout class="p-4 m-2 bg-white/20 rounded-lg h-12"> </gridLayout>
        </Template>
      </listView>
    </tabViewItem>
    <tabViewItem title="Saved" iconSource="sys://star.fill">
      <label text="Second Tab Content" class="text-center text-white"></label>
    </tabViewItem>
    <tabViewItem title="Settings" iconSource="sys://gearshape.fill">
      <label text="Third Tab Content" class="text-center text-white"></label>
    </tabViewItem>
    <tabViewItem iconSource="res://ns-logo" role="search">
      <label text="Third Tab Content" class="text-center text-white"></label>
    </tabViewItem>
  </tabView>
</page>
