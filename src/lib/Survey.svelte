<script>
  import { Model } from "survey-core";
  import "survey-js-ui";
  import "survey-core/defaultV2.min.css";
  import { onMount } from 'svelte';

  export let surveyElement;

  const json = {
  "elements": [
      {
        "type": "radiogroup",
        "name": "car",
        "title": "Which is the brand of your car?",
        "isRequired": true,
        "showNoneItem": true,
        "showOtherItem": true,
        "colCount": 1,
        "choices": [ "Ford", "Vauxhall", "Volkswagen", "Nissan", "Audi", "Mercedes-Benz", "BMW", "Peugeot", "Toyota" ],
        "separateSpecialChoices": true,
        "showClearButton": true
      }
    ],
    "showQuestionNumbers": false
  };
  const survey = new Model(json);
  
  onMount(() => {
		survey.render(surveyElement);
	});

</script>

<div bind:this={surveyElement} class="survey-container"></div> 
