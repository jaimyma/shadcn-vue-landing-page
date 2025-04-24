<script setup lang="ts">
import {
  Card,
  CardDescription,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

import { Badge } from "@/components/ui/badge";

enum ProService {
  YES = 1,
  NO = 0,
}

interface ServiceProps {
  title: string;
  pro: ProService;
  description: string;
}

const serviceList: ServiceProps[] = [
  {
    title: "Personalized Workout Plans",
    description:
      "Receive customized workout plans tailored to your fitness level, goals, and preferences.",
    pro: 0,
  },
  {
    title: "Nutrition Tracking",
    description:
      "Track your daily nutrition and macros to ensure you're fueling your body properly for optimal performance.",
    pro: 0,
  },
  {
    title: "Progress Monitoring",
    description:
      "Monitor your strength, endurance, and other key performance metrics to see your progress over time.",
    pro: 0,
  },
  {
    title: "Virtual Coaching Sessions",
    description:
      "Get real-time guidance and adjustments from professional trainers to improve your form and results.",
    pro: 0,
  },
];
</script>

<template>
  <section
    id="services"
    class="container py-24 sm:py-32"
  >
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
      Services
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      Achieve Your Fitness Goals
    </h2>
    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      Whether you're looking to bulk up, get lean, or improve your endurance, we offer the tools and support to help you succeed.
    </h3>
    
    <div class="grid sm:grid-cols-2 lg:grid-cols-2 gap-4 w-full lg:w-[60%] mx-auto">
      <div
        v-for="{ title, description, pro } in serviceList"
        :key="title"
      >
        <Card class="bg-muted/60 dark:bg-card h-full relative">
          <CardHeader>
            <CardTitle>{{ title }}</CardTitle>
            <CardDescription>{{ description }}</CardDescription>
          </CardHeader>
          <Badge
            v-if="pro === ProService.YES"
            variant="secondary"
            class="absolute -top-2 -right-3"
            >PRO</Badge
          >
        </Card>
      </div>
    </div>
  </section>
</template>

<style lang="less" scoped></style>
