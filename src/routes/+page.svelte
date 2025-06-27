<script>
  import { goto } from '$app/navigation';
  import Navbar from '../lib/Navbar.svelte';
  function goToAddPayment() {
    goto('/add-payment');
  }
</script>


<Navbar />
<style>
  /* global html/body CSS moved to app.html */
  main.fullpage-static {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background: #111;
    z-index: 1;
  }
  .button-add-payment {
    display: flex;
    align-items: center;
    background: #111;
    color: #fff;
    border: 2px solid #e53935;
    border-radius: 8px;
    padding: 0.75rem 1.5rem;
    font-size: 1.1rem;
    font-weight: 500;
    cursor: pointer;
    transition: background 0.2s, border 0.2s;
    gap: 0.75rem;
  }
  .button-add-payment:hover {
    background: #e53935;
    color: #fff;
    border: 2px solid #fff;
  }
  .button-add-payment .plus {
    display: flex;
    align-items: center;
    justify-content: center;
    background: #e53935;
    color: #fff;
    border-radius: 50%;
    width: 2rem;
    height: 2rem;
    font-size: 1.3rem;
    font-weight: bold;
    margin-left: 0.5rem;
    box-shadow: 0 2px 8px rgba(229,57,53,0.15);
  }
</style>
<main class="fullpage-static">
  <button class="button-add-payment" on:click={goToAddPayment}>
    Add Payment Method
    <span class="plus">+</span>
  </button>
</main>
