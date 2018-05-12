---
version: 1.2.0
info:
  title: Reddit
  version: 1.2.0
servers:
- url: www.reddit.com{/r/subreddit}/hot.json
  scheme: https
  asyncapi_servers_variables:
    g:
      description: one of (GLOBAL, US, AR, AU, BG, CA, CL, CO, HR, CZ, FI, GR, HU,
        IS, IN, IE, JP, MY, MX, NZ, PH, PL, PT, PR, RO, RS, SG, SE, TW, TH, TR, GB,
        US_WA, US_DE, US_DC, US_WI, US_WV, US_HI, US_FL, US_WY, US_NH, US_NJ, US_NM,
        US_TX, US_LA, US_NC, US_ND, US_NE, US_TN, US_NY, US_PA, US_CA, US_NV, US_VA,
        US_CO, US_AK, US_AL, US_AR, US_VT, US_IL, US_GA, US_IN, US_IA, US_OK, US_AZ,
        US_ID, US_CT, US_ME, US_MD, US_MA, US_OH, US_UT, US_MO, US_MN, US_MI, US_RI,
        US_KS, US_MT, US_MS, US_SC, US_KY, US_OR, US_SD)
    after:
      description: fullname of a thing
    before:
      description: fullname of a thing
    count:
      description: 'a positive integer (default: 0)'
    limit:
      description: 'the maximum number of items desired (default: 25, maximum: 100)'
    show:
      description: (optional) the string all
    sr_detail:
      description: (optional) expand subreddits
    /r/subreddit:
      description: The subreddit.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/{_r_subreddit}_hot_json'
---