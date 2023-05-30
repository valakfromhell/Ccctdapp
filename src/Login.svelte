<script>
  import { user } from './user';

  let username;
  let password;

  function login() {
    user.auth(username, password, ({ err }) => err && alert(err));
  }

  function signup() {
    user.create(username, password, ({ err }) => {
      if (err) {
        alert(err);
      } else {
        login();
      }
    });
  }
  export let linkText = 'Click Here For Terms and Conditions';
  export let url = 'Users/yogendra/ccctdapp/terms.html';
</script>

<label for="username">Username</label>
<input name="username" bind:value={username} minlength="3" maxlength="16" />

<label for="password">Password</label>
<input name="password" bind:value={password} type="password" />

<button class="login" on:click={login}>Login</button>
<button class="login"  on:click={signup}>Sign Up</button>
  
<h4>Please Make Sure To Respect The End User And Not Spam Any Messages Also The Use Of Profanity Is Discouraged</h4>



<h5>Note: By Signing up you are Agreeing to the Terms and Conditions of CCCT chatroom You Can Read The Terms And Conditions Of CCCT Chatroom By Clicking In the Link Below</h5>
<a href={url}>{linkText}</a>