<script setup lang="ts">
import {
  Accordion,
  AccordionContent,
  AccordionItem,
  AccordionTrigger,
} from "@/components/ui/accordion";

interface FAQProps {
  question: string;
  answer: string;
  value: string;
}

const FAQList: FAQProps[] = [
  {
    question: "How easy is it to get started with Scholatech?",
    answer: "Getting started is straightforward. We offer a guided setup process where we help you configure your school profile, import your existing data, and train your staff. Most schools are up and running within a few days.",
    value: "item-1",
  },
  {
    question: "Can Scholatech handle multiple branches or locations?",
    answer: "Yes, our Enterprise plan supports multi-branch management. You can manage multiple locations from a single dashboard while maintaining separate data and reporting for each branch.",
    value: "item-2",
  },
  {
    question: "What kind of support do you provide?",
    answer: "We provide email support for all plans, with priority support for Professional users and dedicated support for Enterprise customers. We also offer comprehensive documentation, video tutorials, and regular training sessions.",
    value: "item-3",
  },
  {
    question: "Is it possible to customize Scholatech for my school's specific needs?",
    answer: "Yes, Scholatech is highly customizable. While our base features cover most tutoring school needs, we can work with you to adapt the system to your specific requirements, especially on our Enterprise plan.",
    value: "item-4",
  },
  {
    question: "How secure is our school's data?",
    answer: "We take data security seriously. All data is encrypted both in transit and at rest, we perform regular backups, and we comply with relevant data protection regulations. Our systems are hosted on secure cloud infrastructure with industry-standard security measures.",
    value: "item-5",
  },
  {
    question: "Can I migrate data from my existing systems?",
    answer: "Yes, we provide data migration tools and assistance to help you transfer data from your existing systems. We support imports from common formats like Excel, CSV, and can work with you to migrate from other management systems.",
    value: "item-6",
  },
];
</script>

<template>
  <section
    id="faq"
    class="container md:w-[700px] py-24 sm:py-32"
  >
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider">FAQs</h2>
      <h2 class="text-3xl md:text-4xl text-center font-bold">
        Frequently Asked Questions
      </h2>
    </div>

    <Accordion
      type="single"
      collapsible
      class="AccordionRoot"
    >
      <AccordionItem
        v-for="{ question, answer, value } in FAQList"
        :key="value"
        :value="value"
      >
        <AccordionTrigger class="text-left"> {{ question }} </AccordionTrigger>
        <AccordionContent>{{ answer }}</AccordionContent>
      </AccordionItem>
    </Accordion>

    <h3 class="font-medium mt-4 text-center">
      Still have questions?
      <a
        href="#contact"
        class="text-primary underline hover:text-primary/80"
        >Contact our team</a
      >
    </h3>
  </section>
</template>