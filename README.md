# Women Who Design

Women Who Design is a Twitter directory of accomplished women in the design industry. It aims to help people find notable and relevant voices to follow on Twitter by parsing Twitter bios for popular keywords.

### Things Women Who Design can help you with:

- **If you're a Twitter user, use this project to diversify the voices in your feed** Run [proporti.onl](https://www.proporti.onl/) to check the ratio of the people you follow on Twitter. If you're following more men than women, follow women who are work on your areas of interest. Be aware that a feed of white women is not diverse.
- **If you're a hiring manager, use this project to find candidates.** Examine the ratio of senior men to senior women in your organization. Are women of color equally represented? Consider hiring women into promotions above their current role.
- **If you're organizing a conference, use this project to find speakers.** Ensure that the women's speaking slots are as prominent as the men's. Are women of color equally represented? Consider reaching out to women who have never given a talk before.
- **If you have a podcast, use this project to find new guests.** Be mindful of interruptions and ensure that your women guests get equal speaking time. Are women of color equally represented? Consider inviting women who don't already have an audience.

## Forking this project

Women Who Design is happy to support new directories highlighting underrepresented or marginalized groups by providing its source code.

### Prerequisites

This project requires API keys from [Twitter](https://twitter.com) to populate the profile data and [Seeker](https://seeker.company) to populate the job posts.

#### Seeker

Seeker is optional. To run this project without Seeker:

1. Delete the `gatsby-source-seeker plugin` (lines 11-16) from the `gatsby-config.js` file
2. Delete the entire `gatsby-node.js` file
3. Delete the `src/pages/jobs.js` file
4. Remove the link to the jobs page from the `src/components/nav` file

#### Twitter

Twitter is required.

Start by creating an app on the [Twitter developer dashboard](https://developer.twitter.com/en/apps). Select the "Read only" access option.

On lines 6 and 7 of the `gatsby-config.js` file, replace `process.env.WWD_TWITTER_CONSUMER_KEY` with the consumer key from the "Keys and tokens" page of your app's developer dashboard.

Generate a bearer token by running this command in your terminal, replacing the variables with your consumer key and secret information.

```
curl -u "$CONSUMER_KEY:$CONSUMER_SECRET" \
    --data 'grant_type=client_credentials' \
    'https://api.twitter.com/oauth2/token'

```

Copy the bearer token and on line 8, replace `process.env.WWD_TWITTER_BEARER TOKEN` with it.
