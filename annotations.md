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

## Potential Intervention Points:
- Sidekiq
- Puma
