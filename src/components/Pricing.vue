<script setup lang="ts">
import { Button } from '@/components/ui/button';
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from '@/components/ui/card';
import { Check } from 'lucide-vue-next';

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
    title: 'Starter',
    popular: 0,
    price: 99,
    description:
      'Perfect for small tutoring centers just getting started with up to 50 students.',
    buttonText: 'Start Free Trial',
    benefitList: [
      'Up to 50 students',
      'Basic attendance tracking',
      'Course management',
      'Payment tracking',
      'Email support',
      'Basic reporting',
    ],
  },
  {
    title: 'Professional',
    popular: 1,
    price: 199,
    description:
      'Ideal for growing centers with advanced management needs and up to 200 students.',
    buttonText: 'Get Started',
    benefitList: [
      'Up to 200 students',
      'Advanced attendance system',
      'Financial management suite',
      'Document management',
      'Priority support',
      'Advanced analytics',
    ],
  },
  {
    title: 'Enterprise',
    popular: 0,
    price: 399,
    description: 'Custom solution for large institutions with complex requirements.',
    buttonText: 'Contact Us',
    benefitList: [
      'Unlimited students',
      'Custom integrations',
      'Multi-branch management',
      'API access',
      'Dedicated support',
      'Custom reporting',
    ],
  },
];
</script>

<template>
  <section id="pricing" class="container py-24 sm:py-32">
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">Pricing</h2>
    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">Choose Your Plan</h2>
    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground pb-14">
      Flexible pricing options to support your school's growth. All plans include core
      management features.
    </h3>

    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8 lg:gap-4">
      <Card
        v-for="{ title, popular, price, description, buttonText, benefitList } in plans"
        :key="title"
        :class="{
          'drop-shadow-xl shadow-black/10 dark:shadow-white/10 border-[1.5px] border-primary lg:scale-[1.1]':
            popular === PopularPlan?.YES,
        }"
      >
        <CardHeader>
          <CardTitle class="pb-2">
            {{ title }}
          </CardTitle>
          <CardDescription class="pb-4">{{ description }}</CardDescription>
          <div>
            <span class="text-3xl font-bold">${{ price }}</span>
            <span class="text-muted-foreground"> /month</span>
          </div>
        </CardHeader>

        <CardContent class="flex">
          <div class="space-y-4">
            <span v-for="benefit in benefitList" :key="benefit" class="flex">
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
