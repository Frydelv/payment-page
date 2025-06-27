
<script>
  import { goto } from '$app/navigation';
  function goLogin() { goto('/login'); }
  function goRegister() { goto('/register'); }
</script>

<nav class="navbar">
  <div class="navbar-left">
    <span class="logo"><span class="logo-red">F</span>RYDE</span>
  </div>
  <div class="navbar-right">
    <button class="nav-link nav-btn" on:click={goLogin} type="button">Login</button>
    <button class="nav-link nav-btn" on:click={goRegister} type="button">Register</button>
  </div>
</nav>

<style>
.navbar {
  width: 100vw;
  background: #151515;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0.75rem 2.5rem;
  box-sizing: border-box;
  border-bottom: 1px solid #222;
}
.logo {
  font-size: 2rem;
  font-weight: 900;
  color: #fff;
  letter-spacing: 1px;
}
.logo-red {
  color: #e53935;
}
.navbar-right {
  display: flex;
  gap: 1.5rem;
}
.nav-link {
  color: #fff;
  text-decoration: none;
  font-weight: 600;
  font-size: 1rem;
  transition: color 0.2s;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
}
.nav-link:hover {
  color: #e53935;
}
</style>
