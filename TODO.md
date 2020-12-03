- [ ] update license

    unlicensed
- [ ] Add "Example Workflows"?

    this we can remove
- [ ] Update servers urls

- [ ] Maybe remove "kind" parameter from tokenCheck response

    let's just leave it there and improve description
- [ ] Do we really need the ip object in the response when authenticating a navigator?

    This we can remove
- [ ] We never use the retryable param in the response, do we need to include it?

    We're keeping this, because the backend uses it
- [ ] /organizations/{slug} includes `twofactor_enabled` in the response, but we do nothing with it.

    This we can remove

- [ ] /organizations/{slug} includes `write_ehr_changes` in the response, but we do nothing with it.

    This we can remove
- [ ] /organizations/{slug} includes `disable_ip_pinning` in the response, but we do nothing with it. I also didn't know what to write as a description.

    This we can remove
- [ ] /organizations/{slug} includes `check_passwords_against_leaks` in the response. Do we actually do anything with it?

    This we can remove
- [ ] /organizations/{slug} includes `phone_login_enabled` in the response. I don't know what this does and didn't know what to write as a description.

    This we can remove
- [ ] GET /navigators includes "meta.data_key" in the response, but we do nothing with it. Didn't add description.

    This we can remove
- [ ] what are the possible values for sort[key] when fetching Navigators?

    Possible values are "name" and "updated_at"
- [ ] Channel schema includes `verified`. I'm not sure what that is

    This we can remove
- [ ] Channel schema includes `uuid`. I'm not sure what that is

    Investigate a bit more and maybe remove
- [ ] Channel schema includes `authenticated`. I'm not sure what that is

    Investigate a bit more and maybe remove
- [ ] Channel schema includes `meta.type`. I'm not sure what that is. Didn't add description.

    This we can remove
- [ ] Channels sometimes include `owner_type` and `owner_id` and sometimes they don't. Could we make this consistent? We wrote a workaround for this in the frontend.

    We'll investigate this and try and make it consistent
- [ ] Navigator schema includes `clinician_id` which I believe we don't use. Didn't add description

    Bofa uses this, so we're keeping it
- [ ] Navigator schema includes `preferred_medium` which I believe we don't use. Didn't add description

    Investigate and maybe remove
- [ ] When fetching the navigators list, we include the unread_mention_count but not unread_count nor unknown_count. When we fetch just one navigator, we include all 3 counts.

    Remove unread_mention_count when fetching the navigator list
- [ ] Specify which fields are required/valid when updating a ccm

- [ ] Specify which fields are required/valid when creating a ccm
- [ ] Specify which fields are required/valid when updating a patient
- [ ] Specify which fields are required/valid when creating a patient
- [ ] Specify which fields are required/valid when updating a navigator
- [ ] Specify which fields are required/valid when creating a navigator
- [ ] Specify which fields are required/valid when updating a channel
- [ ] Specify which fields are required/valid when creating a channel

- [ ] What's `extra` in the patient schema for? and what are some examples of it?
- [ ] We're not using patient.mrn; do we want to keep it?
- [ ] What are patient.source possible values?
- [ ] What is patient.default_medium?
- [ ] Add responses for when required fields are missing or fields are invalid
- [ ] Make sure all requests with params have 404's
- [ ] Create separate schema with patient properties in interaction.patient
- [ ] What's interaction.spec.source and what are its possible values?
- [ ] What's interaction.spec.incoming_message_id?
- [ ] What's message.title?
- [ ] What are all message.status possible values?
- [ ] What's message.id_from_channel?
