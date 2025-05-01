<script>
  import { Label, Timepicker } from 'flowbite-svelte';
  import { ClockSolid } from 'flowbite-svelte-icons';
</script>

<Label>Select Time (Flowbite Icon):</Label>
<Timepicker icon={ClockSolid} />

<Label>Select Time (Default icon):</Label>
<Timepicker />
