<script setup lang="ts">
import { ChevronsDown } from "lucide-vue-next";
</script>

<template>
  <footer id="footer" class="container py-24 pb-16 sm:py-32 sm:pb-24">
    <div class="p-10 bg-muted/50 dark:bg-card border rounded-2xl">
      <div class="grid grid-cols-2 md:grid-cols-4 xl:grid-cols-6 gap-x-12 gap-y-8">
        <!-- Logo and Description -->
        <div class="col-span-full xl:col-span-2">
          <a href="#" class="flex font-bold items-center">
            <ChevronsDown class="bg-gradient-to-tr from-[#0057B8] via-[#0057B8]/70 to-[#0057B8] rounded-lg w-9 h-9 mr-2 border text-white" />
            <h3 class="text-2xl">Scholatech</h3>
          </a>
          <p class="mt-4 text-sm text-muted-foreground">
            Empowering tutoring schools with comprehensive management solutions.
          </p>
        </div>

        <!-- Product Links -->
        <div class="flex flex-col gap-2">
          <h3 class="font-bold text-lg">Product</h3>
          <a href="#features" class="opacity-60 hover:opacity-100">Features</a>
          <a href="#pricing" class="opacity-60 hover:opacity-100">Pricing</a>
          <a href="#faq" class="opacity-60 hover:opacity-100">FAQ</a>
        </div>

        <!-- Documentation Links -->
        <div class="flex flex-col gap-2">
          <h3 class="font-bold text-lg">Documentation</h3>
          <a href="#" class="opacity-60 hover:opacity-100">Documentation</a>
          <a href="#" class="opacity-60 hover:opacity-100">API Reference</a>
          <a href="#" class="opacity-60 hover:opacity-100">Updates</a>
          <a href="#contact" class="opacity-60 hover:opacity-100">Contact</a>
        </div>

        <!-- Resources -->
        <div class="flex flex-col gap-2">
          <h3 class="font-bold text-lg">Resources</h3>
          <a href="#" class="opacity-60 hover:opacity-100">Knowledge Base</a>
          <a href="#testimonials" class="opacity-60 hover:opacity-100">Success Stories</a>
          <a href="#" class="opacity-60 hover:opacity-100">Privacy Policy</a>
          <a href="#" class="opacity-60 hover:opacity-100">Terms of Service</a>
          <a href="#" class="opacity-60 hover:opacity-100">Security</a>
        </div>

        <!-- Developer Contacts -->
        <div class="flex flex-col gap-2">
          <h3 class="font-bold text-lg">Developer</h3>
          <a href="mailto:a.khchai@gmail.com" class="text-sm text-muted-foreground hover:text-primary">Contact Developer</a>
          <a href="https://ahmedkhchai.fr" target="_blank" class="text-sm text-muted-foreground hover:text-primary">Portfolio</a>
        </div>
      </div>
    </div>
  </footer>
</template>