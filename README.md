# danger-plugin-jira-issue

[![Build Status](https://travis-ci.org/macklinu/danger-plugin-jira-issue.svg?branch=master)](https://travis-ci.org/macklinu/danger-plugin-jira-issue)
[![npm version](https://badge.fury.io/js/danger-plugin-jira-issue.svg)](https://badge.fury.io/js/danger-plugin-jira-issue)

> [Danger](https://github.com/danger/danger-js) plugin to link JIRA issue in pull request

## Usage

Install:

```sh
yarn add danger-plugin-jira-issue --dev
```

At a glance:

```js
// dangerfile.js
import jiraIssue from 'danger-plugin-jira-issue'

jiraIssue({
  key: 'JIRA',
  url: 'https://myjira.atlassian.net/browse',
})
```

With JIRA-123 in the PR title, Danger will comment with:

<table>
  <thead>
    <tr>
      <th width="50"></th>
      <th width="100%" data-danger-table="true">Messages</th>
    </tr>
  </thead>
  <tbody><tr>
      <td>:book:</td>
      <td>:paperclip: <a href="https://myjira.atlassian.net/browse/JIRA-123">JIRA-123</a></td>
    </tr>
  </tbody>
</table>

<p align="right">
  Generated by :no_entry_sign: <a href="http://github.com/danger/danger-js/">dangerJS</a>
</p>

If you work with multiple JIRA project boards, you can supply multiple project keys:

```js
jiraIssue({
  key: ['ABC', 'DEF'],
  url: 'https://myjira.atlassian.net/browse',
})
```

This plugin will recognize issues starting with those keys (e.g. `ABC-123` and `DEF-234`).

You can also supply an optional `format` option, which is a function that receives an array of formatted JIRA URLs and returns a string.

```js
jiraIssue({
  key: 'ABC',
  url: 'https://myjira.atlassian.net/browse',
  format(urls) {
    return `Check out these awesome tickets: ${urls.join(', ')}`
  },
})
```

## Changelog

See the GitHub [release history](https://github.com/macklinu/danger-plugin-jira-issue/releases).

## Development

Install [Yarn](https://yarnpkg.com/en/), and install the dependencies - `yarn install`.

Run the [Jest](https://facebook.github.io/jest/) test suite with `yarn test`.

This project uses [semantic-release](https://github.com/semantic-release/semantic-release) for automated NPM package publishing.

:heart:
