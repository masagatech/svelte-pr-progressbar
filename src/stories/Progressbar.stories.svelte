<script>
// @ts-nocheck

  import { Meta, Template, Story } from "@storybook/addon-svelte-csf";
  import Progressbar from "./Progressbar.svelte";
</script>

<!-- More on default export: https://storybook.js.org/docs/react/writing-stories/introduction#default-export -->
<!-- More on argTypes: https://storybook.js.org/docs/svelte/api/argtypes -->
<Meta
  title="Example/Progressbar"
  component={Progressbar}
  argTypes={{
    backgroundColor: { control: "color" },
    color: { control: "color" },
    height: { control: "text" }
    // size: {
    //   control: { type: 'select' },
    //   options: ['small', 'medium', 'large'],
    // },
  }}
/>

<!-- More on component templates: https://storybook.js.org/docs/svelte/writing-stories/introduction#using-args -->
<Template let:args>
  <Progressbar {...args} />
</Template>

<!-- More on args: https://storybook.js.org/docs/svelte/writing-stories/args -->
<Story
  name="Bar"
  args={{  
     
  }}
/>
 

