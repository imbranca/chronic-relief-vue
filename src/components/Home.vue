<template>
  <div class="hero__section justify-end section flex flex-col relative pt-20 h-screen is--home w-full">
    <div class="hero__container container">
      <div class="hero__inner-cont pb-4">
        <h1 class="hero__h text-white font-bold text-xl pl-5 relative is--home">
           Professional guidance
           <br/> Long Covid, CFS, and Post-Vaccine Syndrome recovery.
        </h1>
        <button class="mt-2 ml-5 relative hero__btn">
          Book Your Free Consultation
        </button>
        <div class="hero__inner-bg is--red-bg"></div>
        </div>
      </div>
  </div>
  <section class="about flex p-5 flex-col mt-5">
      <!-- <img class="w-10 h-10 mx-auto mb-5" src="@/assets/icons/prob1.png"></img> -->
      <div class="container text-[#7f96ac] max-w-1120px mx-auto bg-white rounded-md w-full">
        <h3 class="font-bold text-2xl">
          Regain Energy and Confidence — Step by Step
        </h3>
        <p class="mt-2">Find Your Way Back to Strength and Balance</p>
        <!-- <p class="mt-2">Are you struggling with Long Covid, Chronic Fatigue Syndrome (CFS), or Post-Vaccine Syndrome?
        Do you feel left alone and uncertain about what’s happening to your body?
        You’re not alone — and recovery is possible.</p> -->
        <p class="mt-2">

      <b>Chronic Relief</b> offers you professional guidance and compassionate support on your path to healing.
        Through a combination of group sessions, individual coaching, and a comprehensive online course, you’ll learn to understand your body, activate your inner resources, and gradually rebuild resilience.
        </p>
        
        <a>Learn more</a>

        <!-- <h3> Are you suffering from Long Covid, CFS, or Post-Vaccine Syndrome? </h3>
        <h3> Do you feel abandoned and unsure about what is happening to your body? </h3>
        <h3> Do you long for professional support on your path to recovery? </h3> -->
        <!-- <h3>
          ​​​​Leidest du unter Long Covid, CFS oder dem Post-Vacc-Syndrom?
        </h3>
        <h3>
          Fühlst du dich alleine gelassen und unsicher was mit deinem Körper passiert?
        </h3>
        <h3>​​Sehnst du dich nach professioneller Unterstützung auf deinem Genesungsweg?

        </h3> -->
      </div>
  </section>
  <section class="services w-full ">
     <div class="services__container container text-white max-w-1120px mx-auto p-4 w-full">
      <h3 class="text-2xl font-bold text-center">Increase your quality of life</h3>
        <div class="services__card text-center p-4 flex flex-col mt-4 rounded-md">
            <b class="text-xl">👥 Group Calls</b>
            <ul class="mt-2">
              <li>6 video calls • 1.5h each</li>
              <li>Exchange about successes</li>
              <li>Supportive community</li>
            </ul>
            <a class="mt-2">Learn more</a>
        </div>
         <div class="services__card text-center p-4 flex flex-col mt-4 rounded-md">
            <b class="text-xl">💬 1:1 Accompaniment</b>
            <ul class="mt-2">
              <li>50-min video sessions</li>
              <li>Chat support Mon–Fri</li>
              <li>Theory & practice</li>
              <li>Personalized care</li>
            </ul>
            <a class="mt-2">Learn more</a>
        </div>
        <div class="services__card text-center p-4 flex flex-col mt-4 rounded-md">
            <b class="text-xl">💻 Online Course</b>
            <ul class="mt-2">
              <li>1-year access • FIT-UP platform</li>
              <li>Theory & exercises</li>
              <li>Learn at your own pace</li>
            </ul>
            <a class="mt-2">Learn more</a>
        </div>
     </div>
  </section>
      <section>
      <div class="container max-w-1120px p-4 text-white bg-[#7f96ac]">
        <h2 class="text-2xl font-bold text-center mt-5">Your Digital Companion: The FIT-UP App</h2>
        <div class="fitup__wrapper flex max-w-700px mx-auto">
          <div class="fitup__description flex justify-center w-1/2">
              <ul class="flex flex-col justify-center">
                <li class="my-2">Access weekly course modules anytime</li>
                <li class="my-2">Track your progress and activities</li>
                <li class="my-2">Explore mindfulness and recovery resources</li>
              </ul>
          </div>
          <img class="fitup__img mx-auto mt-5 w-1/2" src="@/assets/images/fitup-portrait.png" alt="..."/>
        </div>
      </div>
    </section>

  <section class="learning-topics p-4 bg-[#fffaf8]">
      <div class="container max-w-1120px ">
        <h2 class="text-2xl font-bold">Chronic Relief Online Program</h2>
        <p class="mt-2">Your 6-week program is designed to help you understand your body, calm your nervous system, and gradually regain balance and strength. Each week combines theory, practice, and reflection, with guided exercises that support both mental and physical recovery.</p>
      </div>
  </section>

    <section class="learning-topics p-4 bg-[#fffaf8]">
      <div class="container max-w-1120px ">
        <Program :programWeeks="programWeeks"/>
      </div>
    </section>


</template>

<script setup>
import Program from './Program.vue';
  let programWeeks = [{
    icon:"icon",
    title: "Week 1. Understanding the Nervous System",
    description: "Foundations of Regulation & Awareness",
    content: `
      <section>
        <p>Learn how your body reacts to stress, how the nervous system functions, and how awareness can help restore balance.</p>
        <h3>Key Modules:</h3>
        <ul class="list-disc pl-4 mb-2">
          <li>Welcome</li>
          <li>Polyvagal Theory (Parts 1 &amp; 2)</li>
          <li>Evolution &amp; Stress Thresholds</li>
          <li>Types of Stimulation &amp; Essential Factors</li>
          <li>Awareness Exercises (1 &amp; 2)</li>
          <li>Tips for Recovery</li>
        </ul>
        <p>🧘‍♀️ <strong>Focus:</strong> Building safety, understanding stress limits, and increasing body awareness.</p>
      </section>
      `
  },
  {
    icon:"icon",
    title: "Week 2. Mindset & Emotional Regulation",
    description: "Thought Patterns and Emotional Balance",
    content: `
    <section>
      <p>Discover how your thoughts and environment influence your recovery and learn techniques to foster positive change.</p>
      <h3>Key Modules:</h3>
      <ul class="list-disc pl-4 mb-2">
        <li>Positive Thoughts &amp; Vision</li>
        <li>Mindset and 30-Day Challenge</li>
        <li>Stopping Thought Spirals</li>
        <li>Creating Supportive Space and Routine</li>
        <li>Recognizing Progress</li>
        <li>Emotional Regulation &amp; Gratitude</li>
        <li>Wins &amp; Tips for Better Sleep</li>
      </ul>
      <p>💭 <strong>Focus:</strong> Developing emotional stability, self-compassion, and healthy routines.</p>
    </section>
    `
  },
 {
    icon: "🔄",
    title: "Week 3. Brain Retraining & Resource Activation",
    description: "Reprogramming and Recovery in Action",
    content: `
    <section>
      <p>Explore how to retrain your brain’s responses to symptoms and re-establish a sense of safety and calm.</p>
      <h3>Key Modules:</h3>
      <ul class="list-disc pl-4 mb-2">
        <li>Thoughts &amp; Behaviors</li>
        <li>Chronic Pain &amp; Symptom Representation</li>
        <li>Sense of Safety &amp; Baseline Work</li>
        <li>Active Recovery &amp; Breaks</li>
        <li>Understanding Fear</li>
        <li>Nutrition for Recovery</li>
      </ul>
      <p>⚙️ <strong>Focus:</strong> Building new neural pathways and practicing resource-oriented regulation.</p>
    </section>
    `
  },
  {
    icon: "🌊",
    title: "Week 4. Managing Fluctuations & Setbacks",
    description: "Navigating the Ups and Downs of Healing",
    content: `
    <section>
      <p>Learn to identify phases of adaptation and distinguish between setbacks and progress.</p>
      <h3>Key Modules:</h3>
      <ul class="list-disc pl-4 mb-2">
        <li>Primary &amp; Secondary Symptoms</li>
        <li>Adaptation Phases and Crashes</li>
        <li>Mood Swings</li>
        <li>Duration vs. Intensity</li>
      </ul>
      <p>🌱 <strong>Focus:</strong> Building resilience, acceptance, and consistency through cycles of recovery.</p>
    </section>
    `
  },
  {
    icon: "🌅",
    title: "Week 5. Integration & Growth",
    description: "Recognizing Change and Staying the Course",
    content: `
    <section>
      <p>Reflect on your progress and strengthen your long-term motivation for healing.</p>
      <h3>Key Modules:</h3>
      <ul class="list-disc pl-4 mb-2">
        <li>Noticeable Changes</li>
        <li>Letter to the Future</li>
        <li>Micro to Macro Perspective</li>
        <li>Symptom Changes as Progress</li>
        <li>Patience in the Second Half</li>
        <li>Benefits &amp; Tips for Sustainable Recovery</li>
      </ul>
      <p>💪 <strong>Focus:</strong> Reinforcing positive habits and maintaining steady improvement.</p>
    </section>
    `
  },
  {
    icon: "☀️",
    title: "Week 6. Long-Term Recovery & Reintegration",
    description: "Stability and Resilience",
    content: `
    <section>
      <p>Bring together all you’ve learned to support a sustainable, balanced life after recovery.</p>
      <h3>Key Modules:</h3>
      <ul class="list-disc pl-4 mb-2">
        <li>Reaction to Life</li>
        <li>Reinfection &amp; Relapse Prevention</li>
        <li>Understanding Temporary vs. Long-Term Change</li>
        <li>Recovery Reflection &amp; Conclusion</li>
      </ul>
      <p>🌼 <strong>Focus:</strong> Integrating your recovery tools into daily life.</p>
    </section>
    `
  }];

</script>

<style lang="scss">
.max-w-700px{
  max-width: 700px;
}
.hero__section{
  background-image: url('@/assets/images/dsc2099-2_orig.jpg');
  background-size: cover;
}
.hero__inner-bg.is--red-bg {
    background-color: #7f96ac;
}
.hero__section{
  height: 340px;
}
.hero__h{
  z-index: 100;
  width: 60%;
  min-width: 300px;
}
.hero__btn{
  border: solid 2px white;
  color: white;
  padding: 5px;
}
.hero__inner-bg {
    width: 60%;
    position: absolute;
    min-width: 300px;
    height: 160px;
    bottom: 0;
    left: 0;
}

.services__card{
  background-color: rgba(244,247,248,0.2);
}
.services__container{
  background-image: url('@/assets/images/199873492.jpg');

}
.services__card{
  opacity: 0.2px;
}
button{
  z-index: 3;
}

.fitup__img{
  max-width: 250px;
}

</style>