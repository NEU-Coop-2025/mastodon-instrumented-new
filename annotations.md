# Annotations Notes

## REACT-ROUTER

- Opportunity to switch to a more modern and (probably) safer approach of handling routing

### Intervention Effects

- has more features compared to React-Router - see https://tanstack.com/router/latest/docs/framework/react/comparison
- Potential drawbacks include larger bundle size, less community support due to it being relatively new

### Privacy Implications

- Should have minimal privacy concerns as routes commonly do not interact with sensitive data

### TODO:

- Find out whether TanStack Router and other similar routers are compatible with Ruby and Rails & other current setups
- Compare the benefits and drawbacks of replacing react-router with TanStack

## TRENDING-NEW

- Allows the user to filter out previously viewed toots for a more intuitive experience on the trending page

### Privacy Implications

- Potentially gathering user data through seen toots

### TODO:

- Find out where exactly this should be placed in the codebase

## Retention of IP Address - Admin side

- see https://github.com/mastodon/mastodon/issues/6474
- This part allows the admin to be in control of the time they want to retain the users IP address. The current default is 12 months.

### Privacy Implications

- The admin & Mastodon will gain knowledge of the users' IP addresses that potentially is unnessisary. (TODO: see if regilations & laws require Mastodon to have IP addresses of users).

### Related files & discussions

- https://github.com/mastodon/mastodon/blob/main/.env.production.sample - line 84
- https://github.com/mastodon/mastodon/blob/main/config/sidekiq.yml - line 43
- https://github.com/mastodon/mastodon/blob/main/app/workers/scheduler/ip_cleanup_scheduler.rb
- https://github.com/mastodon/mastodon/blob/main/spec/workers/scheduler/ip_cleanup_scheduler_spec.rb
- https://github.com/mastodon/mastodon/issues/6474

## Trending_Threshold

- It seems that the current trending page is designed to show what the current instance's users are reblogging.
- Threshold of at least 5 reblogs.
- This is to perserve user privacy for small sized instances.
- I am unsure whether this is needed as if a user reblog/boost a post, as far as I am aware, it will be visible in their profile page. So this to me harms the UX without actually preserving privacy.

### Related files & discussions

- https://github.com/mastodon/mastodon/discussions/21208
- https://github.com/mastodon/mastodon/blob/v4.0.2/app/models/trends/statuses.rb#L103

### TODO:

- look into relays and how that could affect UX & privacy

## Trending_Overhaul

- change the trending requirements from reboosts to the total of reboosts, favorites, and bookmarks.
- reposts and pin can work as a public bookmark system.

## Potential Intervention Points:

- Sidekiq
- Puma
