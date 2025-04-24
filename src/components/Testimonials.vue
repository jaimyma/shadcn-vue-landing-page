<script setup lang="ts">
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar";

import {
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

import {
  Carousel,
  CarouselContent,
  CarouselItem,
  CarouselNext,
  CarouselPrevious,
} from "@/components/ui/carousel";

import { Star } from "lucide-vue-next";

interface ReviewProps {
  image: string;
  name: string;
  userName: string;
  comment: string;
  rating: number;
}

const reviewList: ReviewProps[] = [
  {
    image: "https://github.com/shadcn.png",
    name: "Michael Harris",
    userName: "Software Engineer",
    comment:
      "I’ve been using this platform for months and it has significantly improved my productivity. The user interface is so smooth",
    rating: 5.0,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Emily Smith",
    userName: "Marketing Specialist",
    comment:
      "This tool has streamlined our marketing campaigns and helped us track all our metrics in one place. Highly recommend to anyone",
    rating: 4.9,
  },

  {
    image: "https://github.com/shadcn.png",
    name: "Liam Brown",
    userName: "Product Designer",
    comment:
      "As a designer, I find the customization options amazing. I can adjust everything to match my brand and work more efficiently.",
    rating: 5.0,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Olivia Davis",
    userName: "Data Analyst",
    comment:
      "The analytics tools provided are exactly what I needed. They’ve enabled me to analyze data faster and make better decisions for my team.",
    rating: 4.8,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "James Wilson",
    userName: "Project Manager",
    comment:
      "Managing teams has never been easier! With this platform, I can stay on top of project timelines and ensure everything runs smoothly.",
    rating: 5.0,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Charlotte Johnson",
    userName: "Operations Manager",
    comment:
      "I love how this system integrates with all our other tools. It’s made our operations more efficient and saved us tons of time.",
    rating: 4.9,
  },
];
</script>

<template>
  <section
    id="testimonials"
    class="container py-24 sm:py-32"
  >
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
        Testimonials
      </h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
        Hear What Our 1000+ Clients Say
      </h2>
    </div>

    <Carousel
      :opts="{
        align: 'start',
      }"
      class="relative w-[80%] sm:w-[90%] lg:max-w-screen-xl mx-auto"
    >
      <CarouselContent>
        <CarouselItem
          v-for="review in reviewList"
          :key="review.name"
          class="md:basis-1/2 lg:basis-1/3"
        >
          <Card class="bg-muted/50 dark:bg-card">
            <CardContent class="pt-6 pb-0">
              <div class="flex gap-1 pb-6">
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
              </div>

              "{{ review.comment }}"
            </CardContent>

            <CardHeader>
              <div class="flex flex-row items-center gap-4">
                <Avatar>
                  <AvatarImage
                    src="https://www.radix-vue.com/logo.svg"
                    alt="@radix-vue"
                  />
                  <AvatarFallback>SV</AvatarFallback>
                </Avatar>

                <div class="flex flex-col">
                  <CardTitle class="text-lg">{{ review.name }}</CardTitle>
                  <CardDescription>{{ review.userName }}</CardDescription>
                </div>
              </div>
            </CardHeader>
          </Card>
        </CarouselItem>
      </CarouselContent>
      <CarouselPrevious />
      <CarouselNext />
    </Carousel>
  </section>
</template>
