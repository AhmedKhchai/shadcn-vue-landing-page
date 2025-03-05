<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";
import {
  TrendingUp,
  Users,
  BadgeDollarSign,
  BarChart3,
} from "lucide-vue-next";

interface BenefitsProps {
  icon: string;
  title: string;
  description: string;
}

const benefitList: BenefitsProps[] = [
  {
    icon: "users",
    title: "Increase Student Satisfaction",
    description:
      "Happy students are more likely to enroll in additional courses, recommend your school, and become long-term customers.",
  },
  {
    icon: "badgeDollarSign",
    title: "Reduce Operational Costs",
    description:
      "Identify and eliminate inefficient processes, unprofitable courses, and resource waste through data-driven insights.",
  },
  {
    icon: "trendingUp",
    title: "Drive Revenue Growth",
    description:
      "Target investments toward profitable courses, optimize teacher allocation, and capitalize on seasonal enrollment patterns.",
  },
  {
    icon: "barChart3",
    title: "Better Decision Making",
    description:
      "Make informed decisions with comprehensive analytics covering attendance, payments, performance, and business metrics.",
  },
];

const iconMap: Record<string, any> = {
  users: Users,
  badgeDollarSign: BadgeDollarSign,
  trendingUp: TrendingUp,
  barChart3: BarChart3,
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
          Transform Your School Operations
        </h2>
        <p class="text-xl text-muted-foreground mb-8">
          Join schools like Boosting Centre who have revolutionized their operations and improved their business decisions with Scholatech.
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