<template>
  <div class="min-h-screen bg-gray-200 pt-8">
    <div class="max-w-screen-lg mx-auto rounded bg-white shadow-sm px-8 py-4">
      <div class="text-center underline">Steps to reproduce:</div>
      <ol class="ml-4 mt-4 list-decimal grid grid-cols-2 gap-4">
        <li>
          <div class="text-gray-800 font-bold">Go to the `/about` page:</div>
          <ul class="ml-4 text-sm text-gray-600 list-disc">
            <li>No leave transition</li>
            <li>about enter transition</li>
            <li>console.warn('entering about/index.vue page')</li>
          </ul>
        </li>
        <li>
          <div class="text-gray-800 font-bold">Toggle between `/about` and `/about/me`</div>
          <ul class="ml-4 text-sm text-gray-600 list-disc">
            <li>Enter & Leave transitions working fine</li>
            <li>console.warn('leaving ...') && console.warn('entering ...')</li>
          </ul>
        </li>
        <li>
          <div class="text-gray-800 font-bold">Now go back to `/index`.</div>
          <ul class="ml-4 text-sm text-gray-600 list-disc">
            <li>Here comes the problem.</li>
            <li>Leave transition of the about page is not triggered</li>
            <li>Enter transition of the about page is triggered (see console.warn())</li>
            <li>The opposite should be triggered (leave transition & no enter transition)</li>
          </ul>
        </li>
      </ol>
    </div>

    <Nuxt />
  </div>
</template>
