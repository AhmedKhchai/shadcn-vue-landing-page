<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";
import {
  Users,
  GraduationCap,
  CalendarDays,
  BadgeDollarSign,
  ClipboardCheck,
  LayoutDashboard,
} from "lucide-vue-next";

interface FeaturesProps {
  icon: string;
  title: string;
  description: string;
}

const featureList: FeaturesProps[] = [
  {
    icon: "users",
    title: "Student Management",
    description:
      "Effortlessly manage student profiles, track enrollments, monitor progress, and maintain attendance records in one place.",
  },
  {
    icon: "graduationCap",
    title: "Teacher Management",
    description:
      "Handle teacher assignments, track performance, manage schedules, and process payments seamlessly.",
  },
  {
    icon: "calendarDays",
    title: "Course Management",
    description:
      "Create and manage courses, schedule sessions, track completions, and organize course packs efficiently.",
  },
  {
    icon: "badgeDollarSign",
    title: "Payment Tracking",
    description:
      "Process student payments, manage teacher compensation, apply flexible discounts, and generate financial reports.",
  },
  {
    icon: "clipboardCheck",
    title: "Attendance System",
    description:
      "Track real-time attendance, manage absences, monitor teacher presence, and generate attendance reports.",
  },
  {
    icon: "layoutDashboard",
    title: "Analytics Dashboard",
    description:
      "Access comprehensive analytics for data-driven decisions about courses, teachers, and business performance.",
  },
];

const iconMap: Record<string, any> = {
  users: Users,
  graduationCap: GraduationCap,
  calendarDays: CalendarDays,
  badgeDollarSign: BadgeDollarSign,
  clipboardCheck: ClipboardCheck,
  layoutDashboard: LayoutDashboard,
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
      Comprehensive School Management
    </h2>
    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      Everything you need to run your tutoring school efficiently in one integrated platform. Streamline operations and focus on what matters most - education.
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