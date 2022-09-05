<!-- Treeview.stories.svelte -->

<script>
 import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
 import {Treeview} from '@bexis2/svelte-bexis2-core-ui';
 
 import Data from './Data.svelte';
 import sourceData from '!!raw-loader!./Data.svelte';
 import Events from './Events.svelte';
 import sourceEvents from '!!raw-loader!./Events.svelte';
 import Options from './Options.svelte';
 import sourceOption from '!!raw-loader!./Options.svelte';

 import Example from '../../Example.svelte'

 import sourceJSON from '!!raw-loader!./data.txt'
 import ServerSide from './serverside/ServerSide.svelte'
 import sourceServerSideSvelte from '!!raw-loader!./serverside/ServerSide.svelte'
 import sourceServerSideCSharp from '!!raw-loader!./serverside/server.cs'
 import sourceServerSideModel from '!!raw-loader!./serverside/model.cs'

 let argTypes={
    data: { control: "object" },
    showcheckbox: { control: "boolean" },
    showcount: { control: "boolean" }
  }


  let data =[{
      "label": "Test",
      "description":"description of a",
      "count": 2,
      "value": "A",
      "active":false,
      "href":"http://www.google.de",
      "items": [
        {
        "label": "A1",
        "description":"description of a1",
        "count": 1,
        "value": "1",
        "active":false,
        "items": []
        },
        {
        "label": "A2",
        "description":"description of a2",
        "count": 1,
        "value": "2",
        "active":false,
        "items": [
            {
            "label": "underlaying",
            "description":"description of underlaying",
            "count": 1,
            "value": "underlaying",
            "active":false,
            "items": []
            }
          ]
        }
      ]
  }]

</script>

<Meta title="Bexis2/Frontend/Treeview" 
component={Treeview} 
argTypes={argTypes}
/>

<Template let:args>
 <Treeview {...args}/>
</Template>

<Story name="Playground">
  
</Story>



