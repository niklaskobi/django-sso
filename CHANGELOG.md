### 1.1.4 at 12 January 2023

- In gateway side in Admin panel in "Subordinated services" the token field mode changed to read-write. Reason: If in an service just need to change token and and keep requests stats on. Also this fixes bug, when new instance have different token before and after saving. 
- Fixed critical bug: If an subordinated service is off-line - any login action in the SSO gateway takes exception. Now behavior changed to short timeout of waiting for alive and reply else will skip broadcasting events (Find `SSO_SUBORDINATE_COMMUNICATION_TIMEOUT` variable in [README.md](README.md))
- Documentation updated.
- For superusers allowed deletion in "Single Sign-On › Authentication requests". Reason: Need full control without any developer actions.
- Deauthentication event was not send in SSO mechanism. Now it's works. When user logging out in subordinated service or gateway - user logout everywhere.



### 2.0.0 at 11 February 2023

- Added custom fields to synchronization between gateway and subordinated services.
- Reworked user deletion behavior: If user deleted on the gateway app, on subordinated service it will diabled.
- Fixed identy changing problem: If user email has changed - in old version system was create new user, but not renamed.
- Added `http://your.gateway/sso/debug/update_event/` page on gateway side for debugging additional fields event content.
- Updated README.md
