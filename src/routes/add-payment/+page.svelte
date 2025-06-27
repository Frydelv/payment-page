<script>
  import Navbar from '../../lib/Navbar.svelte';
  import { goto } from '$app/navigation';
  let cardNumber = '';
  let expiry = '';
  let cvc = '';
  let name = '';
  function handleSubmit(e) {
    e.preventDefault();
    alert('Payment method added!');
  }
  function goBack() {
    goto('/');
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
  <form on:submit|preventDefault={handleSubmit} style="background: #181818; padding: 2rem 2.5rem; border-radius: 12px; box-shadow: 0 2px 16px rgba(0,0,0,0.08); min-width: 320px; max-width: 90vw;">
    <h2 style="color: #e53935; text-align: center; margin-bottom: 1.5rem;">Add Payment Method</h2>
    <div style="margin-bottom: 1rem;">
      <label for="name" style="color: #fff;">Name on Card</label><br>
      <input id="name" type="text" bind:value={name} required style="width: 100%; padding: 0.5rem; border-radius: 6px; border: 1px solid #333; background: #222; color: #fff; margin-top: 0.25rem;" />
    </div>
    <div style="margin-bottom: 1rem;">
      <label for="cardNumber" style="color: #fff;">Card Number</label><br>
      <input id="cardNumber" type="text" bind:value={cardNumber} required maxlength="19" pattern="[0-9 ]*" style="width: 100%; padding: 0.5rem; border-radius: 6px; border: 1px solid #333; background: #222; color: #fff; margin-top: 0.25rem;" />
    </div>
    <div style="display: flex; flex-direction: column; gap: 0.75rem; margin-bottom: 1.5rem;">
      <div style="display: flex; gap: 1.5rem;">
        <div style="flex: 1; display: flex; flex-direction: column;">
          <label for="expiry" style="color: #fff;">Expiry</label>
          <input id="expiry" type="text" bind:value={expiry} required maxlength="5" placeholder="MM/YY" style="width: 100%; padding: 0.5rem; border-radius: 6px; border: 1px solid #333; background: #222; color: #fff; margin-top: 0.25rem;" />
        </div>
        <div style="flex: 1; display: flex; flex-direction: column;">
          <label for="cvc" style="color: #fff;">CVC</label>
          <input id="cvc" type="text" bind:value={cvc} required maxlength="4" pattern="[0-9]*" style="width: 100%; padding: 0.5rem; border-radius: 6px; border: 1px solid #333; background: #222; color: #fff; margin-top: 0.25rem;" />
        </div>
      </div>
    </div>
    <button class="button-add-payment" type="submit" style="width: 100%; justify-content: center; margin-bottom: 1rem;">
      Add Payment Method
    </button>
    <button type="button" on:click={goBack} style="width: 100%; justify-content: center; background: transparent; color: #e53935; border: 2px solid #e53935; border-radius: 8px; padding: 0.6rem 0; font-size: 1rem; font-weight: 600; cursor: pointer; transition: background 0.2s, color 0.2s;">
      ← Back
    </button>
  </form>
</main>
