# cf-fullstack-meet-app
CF fullstack meet app


## User story 1: As a user,I should be able to toggle event details So that I see event detail and overview of events

```gherkin
Feature: SHOW/HIDE AN EVENT'S DETAILS
Scenario: An event element is collapsed by default
  Given user is on the Meet app
   Then event details are collapsed
Scenario: User can expand an event to see its details
  Given user is on the Meet app
   When user click on expand event
   Then event details are shown
Scenario: User can collapse an event to hide its details
  Given User is on the Meet app
    And an event is expanded
   When User click on hide event
   Then event details are hidden
```

## User story 2: As a user,I should be able to specify number events So that I see event detail and overview of events

```gherkin
Feature: SPECIFY NUMBER OF EVENTS
Scenario: When user hasn’t specified a number, 32 is the default number
  Given user is on the Meet app
   Then 32 events are shown on the page
Scenario Outline: User can change the number of events they want to see
  Given user is on the Meet app
   When user enter <number_of_events_to_show> on number of events to show input 
   Then <number_of_events_to_show> events are shown on the page
  Examples: 
    | number_of_events_to_show | 
    | 10                       | 
    | 20                       | 
    | 50                       | 
```


## User story 3: As a user, I should be able to use the meet app offline, so that I see event details 

```gherkin
Feature: USE THE APP WHEN OFFLINE
Scenario:  Show cached data when there’s no internet connection
  Given user is on the Meet app
    And user is offline
   Then app shown cached events
Scenario: Show error when user changes the city
  Given user is on the Meet app
    And user is offline
   When user change the city
   Then Show error message "You are offline not possible to change the change the city, try again later"
Scenario: Show error when user changes the time range
  Given user is on the Meet app
    And user is offline
   When user change the time range
   Then Show error message "You are offline not possible to change the time range, try again later"
```

## User story 4: As a user, I should be able to see number events by city, so that I can plan to visit the city

```gherkin
Feature: DATA VISUALIZATION
Scenario: Show a chart with the number of upcoming events in each city
  Given user is on the Meet app
    And user is on charts page
   Then app shown number of events per city charts
```