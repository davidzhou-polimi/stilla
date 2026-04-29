<script lang="ts">
  import Link from './Link.svelte';
</script>

<div class="flex items-center justify-center px-6 py-4 md:px-10 md:py-8 lg:px-20 relative w-full">
  <div class="flex flex-col items-center justify-center w-full lg:w-[640px] h-[54px] md:h-[72px] px-10 relative shrink-0 z-0">
    <!-- Desktop SVG Background -->
    <svg class="absolute inset-0 w-full h-full -z-10 hidden lg:block" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg" width="640" height="72" viewBox="0 0 640 72" fill="none">
      <path d="M0 36C0 6.354 6.1775 0 35 0H605C633.823 0 640 6.354 640 36C640 65.646 633.823 72 605 72H35C6.1775 72 0 65.646 0 36Z" fill="url(#paint0_linear_112_129)"/>
      <defs>
        <linearGradient id="paint0_linear_112_129" x1="320" y1="0" x2="320" y2="72" gradientUnits="userSpaceOnUse">
          <stop stop-color="#3C3734" stop-opacity="0.75"/>
          <stop offset="0.2" stop-color="#3C3734"/>
        </linearGradient>
      </defs>
    </svg>

    <!-- Tablet SVG Background -->
    <svg class="absolute inset-0 w-full h-full -z-10 hidden md:block lg:hidden" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg" width="664" height="72" viewBox="0 0 664 72" fill="none">
      <path d="M0 36C0 6.354 7.06 0 40 0H624C656.94 0 664 6.354 664 36C664 65.646 656.94 72 624 72H40C7.06 72 0 65.646 0 36Z" fill="url(#paint0_linear_112_6)"/>
      <defs>
        <linearGradient id="paint0_linear_112_6" x1="332" y1="0" x2="332" y2="72" gradientUnits="userSpaceOnUse">
          <stop stop-color="#3C3734" stop-opacity="0.75"/>
          <stop offset="0.2" stop-color="#3C3734"/>
        </linearGradient>
      </defs>
    </svg>

    <!-- Mobile SVG Background -->
    <svg class="absolute inset-0 w-full h-full -z-10 block md:hidden" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg" width="354" height="54" viewBox="0 0 354 54" fill="none">
      <path d="M0 27C0 4.7655 4.7655 0 27 0H327C349.235 0 354 4.7655 354 27C354 49.2345 349.235 54 327 54H27C4.7655 54 0 49.2345 0 27Z" fill="url(#paint0_linear_112_98)"/>
      <defs>
        <linearGradient id="paint0_linear_112_98" x1="177" y1="0" x2="177" y2="54" gradientUnits="userSpaceOnUse">
          <stop stop-color="#3C3734" stop-opacity="0.75"/>
          <stop offset="0.2" stop-color="#3C3734"/>
        </linearGradient>
      </defs>
    </svg>
    <div class="flex items-center justify-between relative w-full">
    <div class="flex items-center gap-2 shrink-0">
      <a href="#" class="text-logo text-link-default whitespace-nowrap">Stilla</a>
    </div>
    <div class="flex items-center gap-6 shrink-0">
      <Link href="#">Guide</Link>
      <Link href="#">Percorsi</Link>
    </div>
  </div>
</div>
</div>
