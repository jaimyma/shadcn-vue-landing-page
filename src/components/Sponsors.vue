<script setup lang="ts">
import { Marquee } from "@selemondev/vue3-marquee";
import "@selemondev/vue3-marquee/dist/style.css";

import {
  Dumbbell,
  HeartPulse,
  Bike,
  Mountain,
  Brain,
  Timer,
} from "lucide-vue-next";

interface sponsorsProps {
  icon: string;
  name: string;
}

const sponsors: sponsorsProps[] = [
  {
    icon: "dumbbell",
    name: "Strength",
  },
  {
    icon: "heartpulse",
    name: "Cardio",
  },
  {
    icon: "bike",
    name: "Cycling",
  },
  {
    icon: "mountain",
    name: "Outdoor",
  },
  {
    icon: "brain",
    name: "Mental",
  },
  {
    icon: "timer",
    name: "HIIT",
  },
];

const iconMap: Record<
  string,
  | typeof Dumbbell
  | typeof HeartPulse
  | typeof Bike
  | typeof Mountain
  | typeof Brain
  | typeof Timer
> = {
  dumbbell: Dumbbell,
  heartpulse: HeartPulse,
  bike: Bike,
  mountain: Mountain,
  brain: Brain,
  timer: Timer,
};
</script>

<template>
  <section
    id="sponsors"
    class="max-w-[75%] mx-auto pb-24 sm:pb-32"
  >
    <h2 class="text-lg md:text-xl text-center mb-6">Used For</h2>

    <div class="mx-auto">
      <Marquee
        class="gap-[3rem]"
        :pauseOnHover="true"
        :fade="true"
        innerClassName="gap-[3rem]"
        :loop="true"
      >
        <div
          v-for="{ icon, name } in sponsors"
          :key="name"
        >
          <div class="flex items-center text-xl md:text-2xl font-medium">
            <component
              :is="iconMap[icon]"
              class="mr-2"
              stroke-width="3"
            />
            {{ name }}
          </div>
        </div>
      </Marquee>
    </div>
  </section>
</template>
