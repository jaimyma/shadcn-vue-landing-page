<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
  Sparkle,
  Tag,
  Paintbrush,
  Dumbbell,
  LineChart,
  BarChart,
} from "lucide-vue-next";

interface BenefitsProps {
  icon: string;
  title: string;
  description: string;
}

const benefitList: BenefitsProps[] = [
  {
    icon: "dumbbell",
    title: "Personalized Workouts",
    description:
      "Our AI-powered coach creates customized workout plans tailored to your fitness goals and progress. No more generic routines.",
  },
  {
    icon: "lineChart",
    title: "Track Your Progress",
    description:
      "Monitor your fitness journey with real-time performance tracking and analytics, helping you stay on track towards your goals.",
  },
  {
    icon: "barChart",
    title: "Optimize Performance",
    description:
      "Maximize your results by receiving actionable feedback and adjustments based on your performance data, enhancing your workouts.",
  },
  {
    icon: "sparkle",
    title: "Stay Motivated",
    description:
      "With AI-powered insights and motivation boosters, our coach helps you stay focused and committed to achieving your fitness goals.",
  },
];

const iconMap: Record<
  string,
  | typeof Sparkle
  | typeof Tag
  | typeof Paintbrush
  | typeof Dumbbell
  | typeof LineChart
  | typeof BarChart
> = {
  sparkle: Sparkle,
  tag: Tag,
  paintbrush: Paintbrush,
  dumbbell: Dumbbell,
  lineChart: LineChart,
  barChart: BarChart,
};
</script>

<template>
  <section
    id="benefits"
    class="container py-24 sm:py-32"
  >
    <div class="grid lg:grid-cols-2 place-items-center lg:gap-24">
      <div>
        <h2 class="text-lg text-primary mb-2 tracking-wider">Benefits</h2>

        <h2 class="text-3xl md:text-4xl font-bold mb-4">
          Your AI Coach for Peak Performance
        </h2>
        <p class="text-xl text-muted-foreground mb-8">
          Achieve your fitness goals faster with personalized guidance, progress tracking, and constant motivation. Experience the future of training.
        </p>
      </div>

      <div class="grid lg:grid-cols-2 gap-4 w-full">
        <Card
          v-for="({ icon, title, description }, index) in benefitList"
          :key="title"
          class="bg-muted/50 dark:bg-card hover:bg-background dark:hover:bg-background transition-all delay-75 group/number"
        >
          <CardHeader>
            <div class="flex justify-between">
              <component
                class="size-8 mb-6 text-primary"
                :is="iconMap[icon]"
              />

              <span
                class="text-5xl text-muted-foreground/15 font-medium transition-all delay-75 group-hover/number:text-muted-foreground/30"
                >0{{ index + 1 }}</span
              >
            </div>

            <CardTitle>{{ title }}</CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>
