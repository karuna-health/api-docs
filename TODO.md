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

    This we can remove
- [ ] We're not using patient.mrn; do we want to keep it?

    We're keeping this. (we need to clean up how we handle 3rd party identifiers)
- [ ] What are patient.source possible values?

      enum source: { unspecified: created manually, anonymous: unknown sender, enrolled_from_anonymous: started as unknown and then was created as new patient, flat_file: 5 }
- [ ] What is patient.default_medium?

    Either defualt channel ID or default medium, if no default channel ID, default medium should be async. "This is async if there is no default channel ID set for this patient"
- [ ] Add responses for when required fields are missing or fields are invalid
- [ ] Make sure all requests with params have 404's
- [ ] Create separate schema with patient properties in interaction.patient
- [ ] What's interaction.spec.incoming_message_id?

    It's only present for incomming messages. it's the definitive source to know whether the interaction was incoming
- [ ] What's message.title?

    Present in emails. Optional attribute that's only set when the message is delivered via a medium that supports titles like emails.
- [ ] What are all message.status possible values?

    https://github.com/karuna-health/nyse/blob/master/app/models/message.rb
      enum status: {
    scheduled: 0,
    pending: 1,
    failed: 2,
    delivered: 3,
    read: 4,
    acknowledged: 5,
    cancelled: 6,
    rejected: 7,
    inflight: 8,
    accepted: 9,
  }
- [ ] What's message.id_from_channel?

    3rd party identifier from downstream providers
