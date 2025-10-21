<template>
  <div class="flex program__item w-full p-4 bg-white my-2 rounded-md flex-col" 
      :class="{ 'active': index === currentIndex }"
      :key="index"
      v-on:click="setCurrentIndex(index)"
      v-for="(week, index) in programWeeks">
      <!--Only for desktop-->
      <div class="program__header flex">
        <div class="program__icon">
        </div>
        <div class="program__information">
          <div class="program__title text-xl">{{ week.title }}</div>
          <div class="program__description text-base">{{ week.description }}</div>
        </div>
        <div class="program__icon-wrapper w-20 flex ml-auto">
          <ChevronRight v-if="index !== currentIndex" class="my-auto ml-auto"/>
          <ChevronDown v-else class="my-auto ml-auto"/>
        </div>
      </div>
      <div class="program__body mt-4">
          <div class="program__expanded" v-html="week.content">
        </div>
      </div>
  </div>
  <div class="flex program__item w-full p-4 bg-white my-2 rounded-md flex-col">
     <div class="program__title text-xl mt-2">Practical Exercises (All Weeks)</div>
     <div class="program__description text-base mt-2">Alongside the weekly lessons, you’ll find 42 practical exercises that support your body’s natural recovery processes:</div>
      <ul class="list-disc pl-4 mb-2 mt-2">
          <li>Breathing Exercises – Calm the nervous system</li>
          <li>Mobilization Exercises – Restore movement and balance</li>
          <li>Stretching Exercises – Release tension and improve flexibility</li>
          <li>Nerve Mobilization Exercises – Support neural recovery</li>
          <li>Releasing Neck Tension – Reduce headaches and stress</li>
          <li>Somatic Exercises – Strengthen mind-body awareness</li>
      </ul>
  </div>
</template>
<script setup>
  import {ChevronDown, ChevronRight} from 'lucide-vue-next';
  import {ref, defineProps} from 'vue';

  const props = defineProps({
    programWeeks: Array
  });

//   let programWeeks = [{
//     icon:"icon",
//     title: "Week 1. Understanding the Nervous System",
//     description: "Foundations of Regulation & Awareness",
//     content: `
//       <section>
//         <p>Learn how your body reacts to stress, how the nervous system functions, and how awareness can help restore balance.</p>
//         <h3>Key Modules:</h3>
//         <ul class="list-disc pl-4 mb-2">
//           <li>Welcome</li>
//           <li>Polyvagal Theory (Parts 1 &amp; 2)</li>
//           <li>Evolution &amp; Stress Thresholds</li>
//           <li>Types of Stimulation &amp; Essential Factors</li>
//           <li>Awareness Exercises (1 &amp; 2)</li>
//           <li>Tips for Recovery</li>
//         </ul>
//         <p>🧘‍♀️ <strong>Focus:</strong> Building safety, understanding stress limits, and increasing body awareness.</p>
//       </section>
//       `
//   },
//   {
//     icon:"icon",
//     title: "Week 2. Mindset & Emotional Regulation",
//     description: "Thought Patterns and Emotional Balance",
//     content: `
//     <section>
//       <p>Discover how your thoughts and environment influence your recovery and learn techniques to foster positive change.</p>
//       <h3>Key Modules:</h3>
//       <ul class="list-disc pl-4 mb-2">
//         <li>Positive Thoughts &amp; Vision</li>
//         <li>Mindset and 30-Day Challenge</li>
//         <li>Stopping Thought Spirals</li>
//         <li>Creating Supportive Space and Routine</li>
//         <li>Recognizing Progress</li>
//         <li>Emotional Regulation &amp; Gratitude</li>
//         <li>Wins &amp; Tips for Better Sleep</li>
//       </ul>
//       <p>💭 <strong>Focus:</strong> Developing emotional stability, self-compassion, and healthy routines.</p>
//     </section>
//     `
//   },
//  {
//     icon: "🔄",
//     title: "Week 3. Brain Retraining & Resource Activation",
//     description: "Reprogramming and Recovery in Action",
//     content: `
//     <section>
//       <p>Explore how to retrain your brain’s responses to symptoms and re-establish a sense of safety and calm.</p>
//       <h3>Key Modules:</h3>
//       <ul class="list-disc pl-4 mb-2">
//         <li>Thoughts &amp; Behaviors</li>
//         <li>Chronic Pain &amp; Symptom Representation</li>
//         <li>Sense of Safety &amp; Baseline Work</li>
//         <li>Active Recovery &amp; Breaks</li>
//         <li>Understanding Fear</li>
//         <li>Nutrition for Recovery</li>
//       </ul>
//       <p>⚙️ <strong>Focus:</strong> Building new neural pathways and practicing resource-oriented regulation.</p>
//     </section>
//     `
//   },
//   {
//     icon: "🌊",
//     title: "Week 4. Managing Fluctuations & Setbacks",
//     description: "Navigating the Ups and Downs of Healing",
//     content: `
//     <section>
//       <p>Learn to identify phases of adaptation and distinguish between setbacks and progress.</p>
//       <h3>Key Modules:</h3>
//       <ul class="list-disc pl-4 mb-2">
//         <li>Primary &amp; Secondary Symptoms</li>
//         <li>Adaptation Phases and Crashes</li>
//         <li>Mood Swings</li>
//         <li>Duration vs. Intensity</li>
//       </ul>
//       <p>🌱 <strong>Focus:</strong> Building resilience, acceptance, and consistency through cycles of recovery.</p>
//     </section>
//     `
//   },
//   {
//     icon: "🌅",
//     title: "Week 5. Integration & Growth",
//     description: "Recognizing Change and Staying the Course",
//     content: `
//     <section>
//       <p>Reflect on your progress and strengthen your long-term motivation for healing.</p>
//       <h3>Key Modules:</h3>
//       <ul class="list-disc pl-4 mb-2">
//         <li>Noticeable Changes</li>
//         <li>Letter to the Future</li>
//         <li>Micro to Macro Perspective</li>
//         <li>Symptom Changes as Progress</li>
//         <li>Patience in the Second Half</li>
//         <li>Benefits &amp; Tips for Sustainable Recovery</li>
//       </ul>
//       <p>💪 <strong>Focus:</strong> Reinforcing positive habits and maintaining steady improvement.</p>
//     </section>
//     `
//   },
//   {
//     icon: "☀️",
//     title: "Week 6. Long-Term Recovery & Reintegration",
//     description: "Stability and Resilience",
//     content: `
//     <section>
//       <p>Bring together all you’ve learned to support a sustainable, balanced life after recovery.</p>
//       <h3>Key Modules:</h3>
//       <ul class="list-disc pl-4 mb-2">
//         <li>Reaction to Life</li>
//         <li>Reinfection &amp; Relapse Prevention</li>
//         <li>Understanding Temporary vs. Long-Term Change</li>
//         <li>Recovery Reflection &amp; Conclusion</li>
//       </ul>
//       <p>🌼 <strong>Focus:</strong> Integrating your recovery tools into daily life.</p>
//     </section>
//     `
//   }];

  let currentIndex = ref(null);
  function setCurrentIndex(index){
    if(this.currentIndex != index){
      this.currentIndex = index;
    }else{
      this.currentIndex = null;
    }
  }
</script>

<style lang="scss">
  .program__item{
    border: solid 1px #e7e6e2;
  }
  .program__body {
    display: none;
  }
  .program__item.active .program__body{
    display: flex;
  }
  // .program__item.active .program__icon-wrapper{
  //    transform: rotate(90deg);
  // }
  .program__body p{
    margin-bottom: 10px;
  }
</style>