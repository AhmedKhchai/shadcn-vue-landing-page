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
    image: "boosting-centre.png",
    name: "Sarah El Alami",
    userName: "Director, Boosting Centre",
    comment:
      "Scholatech has transformed how we manage our tutoring center. The attendance tracking and payment management features have saved us countless hours of administrative work.",
    rating: 5.0,
  },
  {
    image: "academic-support.png",
    name: "Mohammed Tazi",
    userName: "Academic Coordinator",
    comment:
      "The course scheduling and teacher management features are exceptional. We can easily match students with the right teachers and track performance effectively.",
    rating: 4.9,
  },
  {
    image: "teacher.png",
    name: "Leila Benjelloun",
    userName: "Lead Mathematics Teacher",
    comment:
      "As a teacher, I love how easy it is to track attendance and manage my schedule. The platform helps me focus more on teaching and less on paperwork.",
    rating: 5.0,
  },
  {
    image: "admin.png",
    name: "Karim Alaoui",
    userName: "School Administrator",
    comment:
      "The analytics dashboard has given us valuable insights into our operations. We've optimized our course offerings and improved our revenue significantly.",
    rating: 4.8,
  },
  {
    image: "parent.png",
    name: "Fatima Zahra",
    userName: "Parent",
    comment:
      "Being able to track my child's attendance and progress through the system has been incredibly helpful. The transparency gives me peace of mind.",
    rating: 5.0,
  },
  {
    image: "finance.png",
    name: "Hassan Berrada",
    userName: "Financial Manager",
    comment:
      "The financial management features are comprehensive and intuitive. Managing payments, discounts, and generating reports has never been easier.",
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
        Trusted by Leading Educational Institutions
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
                    :src="review.image"
                    :alt="review.name"
                  />
                  <AvatarFallback>{{ review.name.charAt(0) }}</AvatarFallback>
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