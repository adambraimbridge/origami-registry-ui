# Origami Registry UI

Get information about Origami components, services, and repositories

## Service Tier

Bronze

## Lifecycle Stage

Production

## Primary URL

https://registry.origami.ft.com

## Host Platform

Heroku

## Contains Personal Data

no

## Contains Sensitive Data

no

## Delivered By

origami-team

## Supported By

origami-team

## Known About By

* jake.champion
* lee.moody
* rowan.manning

## Dependencies

* origami-repo-data
* origami-codedocs

## Healthchecks

* registry.origami.ft.com-https
* origami-registry-ui-eu.herokuapp.com-https

## Failover Architecture Type

ActiveActive

## Failover Process Type

FullyAutomated

## Failback Process Type

FullyAutomated

## Data Recovery Process Type

NotApplicable

## Release Process Type

PartiallyAutomated

## Rollback Process Type

PartiallyAutomated

## Key Management Process Type

Manual

## Architecture

This is a Node.js application, and mostly exists as a presentation layer over the top of the APIs for Origami Repo Data and Origami Codedocs.

Most of the logic for the service is in the routes, and the most complex parts of the app relate to transforming data from the APIs into something that's useable by the view layer.

[Google Drawing](https://docs.google.com/a/ft.com/drawings/d/1qKROLQvR-D5LzxxTTkJgzcr5IlLLkaRh3bEtF0AAYeA/edit?usp=sharing)

## More Information

You can find more information on the live site.

## First Line Troubleshooting

This application is not critical outside of office hours, please contact the Origami team and we'll fix when we're in the office.

If no member of the Origami team is available within office hours, check the status of healthchecks for more information or try restarting all of the dynos across the production Heroku apps ([pipeline here](https://dashboard.heroku.com/pipelines/c206786a-73a4-4cbc-90dc-58db19255704)).


## Second Line Troubleshooting

If the application is failing entirely, you'll need to check a couple of things:

1. Did a deployment just happen? If so, consider rolling it back.
2. Check the Heroku metrics page for EU apps, to see what CPU and memory usage is like ([pipeline here](https://dashboard.heroku.com/pipelines/c206786a-73a4-4cbc-90dc-58db19255704))
3. Check the CDN ([Fastly](https://manage.fastly.com/configure/services/7mnWDqaHxkKwIFASbvnV13/versions/9/domains)) is caching pages as expected.

Always roll back a deploy if one happened just before the thing stopped working – this gives you the chance to debug in the relative calm of QA.

## Monitoring

TODO

## Failover Details

No failover is in place for this because it is a bronze service.

## Data Recovery Details

No data is stored by this system.

## Release Details

The application is deployed to QA whenever a new commit is pushed to the `master` branch of this repo on GitHub. To release to production, a git tag is created and push to GitHub.

## Key Management Details

The only key used by this application is for Origami Repo Data. We rotate this manually.

