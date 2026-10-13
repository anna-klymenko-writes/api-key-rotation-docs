---
title: Rotate an API key without breaking live traffic
description: Replace a Stripe secret API key in production without failed requests.
audience: Backend developers
sources:
  - Tested in my own Stripe sandbox account, October 2026
  - https://docs.stripe.com/keys
  - https://docs.stripe.com/keys-best-practices
---

# Rotate an API key without breaking live traffic

A secret API key is a type of account credential that Stripe uses to authenticate requests from your integration. See [API keys](https://docs.stripe.com/keys).

Rotating a key removes the old key and generates a new one that’s ready to use immediately.

Rotate the key when:

* You lost the key and can’t view it again in the Dashboard.  
* The key was exposed, for example in a public repo, a log file or a chat message, and you need to stop anyone else from using it. Select **Now** in Step 5 of the following procedure.  
* Someone who had access to the key leaves the team or moves to a different role.  
* Your security policy requires rotation on a regular schedule.

## Prerequisites

* Before rotating your key, find every system that uses it, such as servers, scripts, and partner integrations. 
* Open your secrets manager. You'll need to save the new key as soon as you copy it, because in live mode you might not be able to view it again.

## Rotate the API key

1. Go to **Developers** in the bottom-right corner.  
2. Select **API keys**.

<!-- Screenshot: API keys -->

3. Select the three dots icon (**...**) next to the key you want to rotate.  
   

<!-- Screenshot: API keys page with the menu (...) open -->

4. Select **Rotate key**.  
5. Select one of the expiry options in **Set key expiry**:  
* **Now**: the old key stops working immediately and no one can use it anymore. Use this option if the key leaked to stop anyone else from using it.  
        
* **In 1 hour**, **In 24 hours**, **In 3 days**, **In 7 days**: the old key stays active alongside a new one for a selected period of time. Use this option to prevent any breakage in live traffic until you migrate gradually and test the changes.

>[!NOTE]
>If you select **Now**, you must update any code that uses the expired key right away, because systems that still use it start failing immediately.  

<!-- Screenshot: Set key expiry -->

6. Select **Rotate**.

7. In the **Your new secret key** dialog, select **Copy and Close**, then paste the key into your secrets manager right away. In live mode, you might not be able to view it again.

<!-- Screenshot: Copy and Close -->
