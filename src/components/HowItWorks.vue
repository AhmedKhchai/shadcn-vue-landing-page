<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from '@/components/ui/card';
import { Badge } from '@/components/ui/badge';

interface HowItWorksProps {
  badgeTitle: string;
  title: string;
  description: string;
  image: string;
}

const HowItWorksList: HowItWorksProps[] = [
  {
    badgeTitle: 'Setup',
    title: 'Quick and Easy Implementation',
    description:
      "Get started quickly with our guided setup process. We'll help you configure your school profile, import existing data, and customize the system to match your needs.",
    image: 'roboto.png',
  },
  {
    badgeTitle: 'Train',
    title: 'Comprehensive Training',
    description:
      'Our team provides thorough training for administrators, teachers, and staff. Learn to use all features effectively with our hands-on training sessions and documentation.',
    image: 'runner.png',
  },
  {
    badgeTitle: 'Integrate',
    title: 'Seamless Integration',
    description:
      "Integrate Scholatech into your daily operations. We'll help you transition from your existing systems and establish efficient workflows for all processes.",
    image: 'pacheco.png',
  },
  {
    badgeTitle: 'Optimize',
    title: 'Continuous Improvement',
    description:
      'Leverage our analytics to continuously improve your operations. We provide ongoing support and updates to ensure you get the most value from Scholatech.',
    image: 'gamestation.png',
  },
];
</script>

<template>
  <section id="features" class="container py-24 sm:py-32">
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider">How It Works</h2>
      <h2 class="text-3xl md:text-4xl text-center font-bold">
        Get Started With Scholatech
      </h2>
    </div>

    <div class="lg:w-[80%] mx-auto relative">
      <div
        v-for="({ badgeTitle, title, description, image }, index) in HowItWorksList"
        :key="title"
        :class="['flex mb-8 items-center', { ' flex-row-reverse': index % 2 !== 0 }]"
      >
        <Card class="h-full bg-transparent border-0 shadow-none">
          <CardHeader>
            <div class="pb-4">
              <Badge>{{ badgeTitle }}</Badge>
            </div>
            <CardTitle>
              {{ title }}
            </CardTitle>
          </CardHeader>
          <CardContent class="text-muted-foreground w-[80%]">
            {{ description }}
          </CardContent>
        </Card>
        <img
          :src="image"
          :alt="`${title} process illustration`"
          className="w-[150px] md:w-[250px] lg:w-[300px] mx-auto -scale-x-100"
        />
        <div
          :class="[
            '-z-10 absolute right-0 w-44 h-72 lg:w-64 lg:h-80 rounded-full bg-primary/15 dark:bg-primary/10 blur-3xl',
            {
              'left-0': index % 2 !== 0,
            },
          ]"
        ></div>
      </div>
    </div>
  </section>
</template>
