<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
  Dumbbell,
  Target,
  TabletSmartphone,
  ShieldCheck,
  Users,
  Clock,
  Trophy,
  BarChart,
} from "lucide-vue-next";

interface FeaturesProps {
  icon: string;
  title: string;
  description: string;
}

const featureList: FeaturesProps[] = [
  {
    icon: "tabletSmartphone",
    title: "Mobile Friendly",
    description:
      "Access your personalized workout plans and track your progress anytime, anywhere, with our mobile-friendly platform.",
  },
  {
    icon: "target",
    title: "Goal-Oriented Training",
    description:
      "Set your fitness goals and let our AI coach guide you through targeted training programs to help you achieve them faster.",
  },
  {
    icon: "trophy",
    title: "Achieve Success",
    description:
      "Track your milestones and celebrate your achievements. The AI coach rewards your progress with tailored challenges.",
  },
  {
    icon: "users",
    title: "Community Support",
    description:
      "Join a community of like-minded individuals who motivate each other to reach fitness goals and share success stories.",
  },
  {
    icon: "stopwatch",
    title: "Real-Time Feedback",
    description:
      "Receive instant feedback on your workouts to improve your technique, prevent injury, and optimize your performance.",
  },
  {
    icon: "barChart",
    title: "Track Your Progress",
    description:
      "Monitor your performance over time with visual graphs and detailed statistics that show your strength, endurance, and improvements.",
  },
];

const iconMap: Record<
  string,
  | typeof Dumbbell
  | typeof Target
  | typeof TabletSmartphone
  | typeof ShieldCheck
  | typeof Users
  | typeof Clock
  | typeof Trophy
  | typeof BarChart
> = {
  dumbbell: Dumbbell,
  target: Target,
  tabletSmartphone: TabletSmartphone,
  shieldCheck: ShieldCheck,
  users: Users,
  stopwatch: Clock,
  trophy: Trophy,
  barChart: BarChart,
};
</script>

<template>
  <section
    id="features"
    class="container py-24 sm:py-32"
  >
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
      Features
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      What Makes Us Different
    </h2>

    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      Our AI coach is designed to help you reach your fitness goals faster and more effectively. Experience personalized workouts, real-time feedback, and a supportive community.
    </h3>

    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
      <div
        v-for="{ icon, title, description } in featureList"
        :key="title"
      >
        <Card class="h-full bg-background border-0 shadow-none">
          <CardHeader class="flex justify-center items-center">
            <div
              class="bg-primary/20 p-2 rounded-full ring-8 ring-primary/10 mb-4"
            >
              <component
                :is="iconMap[icon]"
                class="size-6 text-primary"
              />
            </div>

            <CardTitle>
              {{ title }}
            </CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground text-center">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>

<style lang="less" scoped></style>
