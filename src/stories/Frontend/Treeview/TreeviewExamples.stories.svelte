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
    data: { control: {disable:true} },
    showcheckbox: { control: {disable:true} },
    showcount: { control:{disable:true}}
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

<Meta title="Bexis2/Frontend/Treeview/Examples" 
component={Treeview}
argTypes={argTypes}
/>

<Template >
  <Treeview/>
 </Template>


<Story name="Data" >
 <Example title="Data" svelte={sourceData} json={sourceJSON}>
  <Data /> 
  <p slot="info">
   How to structure the data for the treeview.
  </p>
 </Example>
 </Story>

 <Story name="Option"  >
  <Example title="Option" svelte={sourceOption} json={sourceJSON}>
   <Options/> 
   <span slot="info">
    How to setup the options.
   </span>
  </Example>
  </Story>

  <Story name="Events"  >
    <Example title="Events" svelte={sourceEvents} json={sourceJSON}>
     <Events/> 
     <span slot="info">
      How to use events.
     </span>
    </Example>
    </Story>

  <Story name="Serverside data loading" >
    <Example title="Serverside data loading" 
      svelte={sourceServerSideSvelte} 
      csharp={sourceServerSideCSharp} 
      model = {sourceServerSideModel}
      codeonly
      stacked>
     <!-- <ServerSide/>  -->
     <span slot="info">
      How to load data from server with a bexis 2 ui model.
     </span>
    </Example>
  </Story>
