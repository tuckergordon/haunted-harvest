<script lang="ts">
  export let date: Date;
  export let style;

  const second = 1000;
  const minute = second * 60;
  const hour = minute * 60;
  const day = hour * 24;

  let remaining;

  const interval = setInterval(() => {
    const now = new Date().getTime();
    const end = date.getTime();
    const distance = end - now;
    const days = Math.floor(distance / day);
    const hours = Math.floor((distance % day) / hour);
    const minutes = Math.floor((distance % hour) / minute);
    const seconds = Math.floor((distance % minute) / second);

    remaining = {
      days,
      hours,
      minutes,
      seconds,
    };

    if (distance < 0) {
      clearInterval(interval);
      // TODO: party has already started
    }
  }, 1000);
</script>

{#if remaining}
  <div {style}>
    {remaining.days}:{remaining.hours}:{remaining.minutes}:{remaining.seconds}
  </div>
{/if}
