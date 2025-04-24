<script setup lang="ts">
import { Button } from "@/components/ui/button";
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

import { Check } from "lucide-vue-next";

enum PopularPlan {
  NO = 0,
  YES = 1,
}

interface PlanProps {
  title: string;
  popular: PopularPlan;
  price: number;
  description: string;
  buttonText: string;
  benefitList: string[];
}

const plans: PlanProps[] = [
  {
    title: "Starter",
    popular: 0,
    price: 0,
    description:
      "Your first steps with the AI Coach. Discover how powerful smart training advice can be.",
    buttonText: "Try for Free",
    benefitList: [
      "Basic AI workout suggestions",
      "Weekly fitness tips",
      "Nutrition checklist",
      "Track 1 goal",
      "Community access",
    ],
  },
  {
    title: "Pro",
    popular: 1,
    price: 45,
    description:
      "Take control of your performance with the full power of your AI Coach at your side.",
    buttonText: "Level Up",
    benefitList: [
      "Real-time AI feedback during workouts",
      "Custom training programs from AI Coach",
      "Meal plans based on your goals",
      "Track unlimited goals & progress",
      "Priority chat with AI Coach",
    ],
  },
  {
    title: "Elite",
    popular: 0,
    price: 120,
    description:
      "You vs. yesterday. For athletes who want every edge. Unleash the full coaching potential.",
    buttonText: "Join Elite",
    benefitList: [
      "Advanced performance insights from AI Coach",
      "Personalized macros & recovery plans",
      "AI-led daily challenges",
      "Private call sessions with AI Coach",
      "Priority support + early feature access",
    ],
  },
];
</script>

<template>
  <section class="container py-24 sm:py-32">
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">Prices</h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">Unlimited access, Unlimited possibilities</h2>

    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground pb-14">
      Choose your plan and start your journey with the AI Coach today. No hidden fees, no contracts.
    </h3>

    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8 lg:gap-4">
      <Card
        v-for="{
          title,
          popular,
          price,
          description,
          buttonText,
          benefitList,
        } in plans"
        :key="title"
        :class="{
          'drop-shadow-xl shadow-black/10 dark:shadow-white/10 border-[1.5px] border-primary lg:scale-[1.1] transform hover:scale-105 transition-transform duration-300':
            popular === PopularPlan?.YES,
        }"
      >
        <CardHeader>
          <CardTitle class="pb-2">{{ title }}</CardTitle>

          <CardDescription class="pb-4">{{ description }}</CardDescription>

          <div class="flex items-baseline">
            <span class="text-3xl font-bold">${{ price }}</span>
            <span class="text-muted-foreground text-lg ml-2">/Month</span>
          </div>
        </CardHeader>

        <CardContent class="flex">
          <div class="space-y-4">
            <span v-for="benefit in benefitList" :key="benefit" class="flex items-center">
              <Check class="text-primary mr-2" />
              <h3>{{ benefit }}</h3>
            </span>
          </div>
        </CardContent>

        <CardFooter>
          <Button
            :variant="popular === PopularPlan?.NO ? 'secondary' : 'default'"
            class="w-full"
          >
            {{ buttonText }}
          </Button>
        </CardFooter>
      </Card>
    </div>
  </section>
</template>

<style scoped>
/* Add some hover effect and animation for the cards */
.card:hover {
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
}
</style>
