<!--
.slide: data-background-image="https://www.nist.gov/sites/default/files/images/2019/09/25/multifactor-authentificaton.png" data-background-opacity="0.2"
-->

# MFA

1. What you knows. (*Knowledge*)
2. What you have. (*Posession*)
3. What you are. (*Inherence*)
4. Where you are.\* (*Location*)

Note:
1. What you knows example: *password*, *PIN code*, *name of your first ~~love~~ school*.
2. What you have example: *OTP*, *YubiKey*, *phone number*, *SMS code*, *on-device prompt*.
3. What you are example: *fingerprint*, *faceID*, *iris data*, *DNA*.
4. Where you are example: *GPS data*, *location of your network*, *last sign-in location*.
---

### Why a <em class="color-yubico-green">Hardware Key?</em>
<img src="https://2.bp.blogspot.com/-2FvyOSlV3f8/XN4qy-LbWjI/AAAAAAAAAiY/m6skYaPJodMJgKv_gxtpvWZCwWulyLfxACLcBGAs/s1600/infographic%25402x.png" width="80%" />
<small style="font-size: 1rem;">
Data from <a href="https://security.googleblog.com/2019/05/new-research-how-effective-is-basic.html"><em>Google Security Blog: How effective is basic account hygiene at preventing hijacking (May 17, 2019)<em></a>
</small>

Note:
At the time of writing (early 2022), 2FA design still centered around preventing automated bot attack. Targeted attack has increasingly become a more [common threat in the industry](https://www.abc.net.au/everyday/protecting-yourself-from-phone-porting-and-sim-card-scams/100421586). In fact, recent draft from NIST recommend [deprecating SMS-based authentication entirely](https://threatpost.com/nist-recommends-sms-two-factor-authentication-deprecation).