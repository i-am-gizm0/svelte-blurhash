<script>
  import { inview } from 'svelte-inview';

  let visible = false
  let hasBeenVisible = false;
  const options = {
    rootMargin: '200px',
  };

  const handleChange = ({detail}) => (hasBeenVisible = (visible = detail.inview) || hasBeenVisible);
</script>

<div use:inview={options} on:change={handleChange}>
  <slot {visible} {hasBeenVisible} />
</div>
