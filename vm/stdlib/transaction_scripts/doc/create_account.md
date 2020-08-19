
<a name="SCRIPT"></a>

# Script `create_account.move`

### Table of Contents

-  [Function `create_account`](#SCRIPT_create_account)



<a name="SCRIPT_create_account"></a>

## Function `create_account`



<pre><code><b>public</b> <b>fun</b> <a href="#SCRIPT_create_account">create_account</a>&lt;TokenType&gt;(account: &signer, fresh_address: address, auth_key_prefix: vector&lt;u8&gt;, initial_amount: u128)
</code></pre>



<details>
<summary>Implementation</summary>


<pre><code><b>fun</b> <a href="#SCRIPT_create_account">create_account</a>&lt;TokenType&gt;(account: &signer, fresh_address: address, auth_key_prefix: vector&lt;u8&gt;, initial_amount: u128) {
  <a href="../../modules/doc/Account.md#0x1_Account_create_account">Account::create_account</a>&lt;TokenType&gt;(fresh_address, auth_key_prefix);
  <b>if</b> (initial_amount &gt; 0) <a href="../../modules/doc/Account.md#0x1_Account_deposit_to">Account::deposit_to</a>(account,
        fresh_address,
        <a href="../../modules/doc/Account.md#0x1_Account_withdraw">Account::withdraw</a>&lt;TokenType&gt;(account, initial_amount)
     );
}
</code></pre>



</details>