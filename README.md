# Weather Mobile App

![Weather App](https://colorfully.eu/wp-content/uploads/2012/06/weather-forecast-facebook-cover.jpg)

Your goal is to create a mobile app that displays the current weather and forecast for the selected location.

## Technologie stack

- App logic: [React Native](https://reactnative.dev/)
- Data fetching & store: [React Query](https://react-query-v3.tanstack.com/), [Tutorial for using with React Native](https://blog.logrocket.com/react-query-state-management-react-native/)
- Persistent app storage: [React Native Async Storage](https://github.com/react-native-async-storage/async-storage)
- Project management:
  - React Native CLI - harder to setup and work with but better for big projects
  - Expo CLI - easier to set up and work with, but has some limitations (recommended option)
    - [Pros & cons for both CLIs](https://levelup.gitconnected.com/react-native-cli-vs-expo-cli-which-one-do-i-choose-bdf02ea457bf)
    - [Setup process](https://reactnative.dev/docs/environment-setup)
- [Typescript](https://docs.expo.dev/guides/typescript/)
- [ESLint, Prettier, and Pre-commit](https://dev-yakuza.posstree.com/en/react-native/eslint-prettier-husky-lint-staged/)

## Roadmap

- Setup your development environment
- Initialize an empty project
- Create a GitHub repo and connect it to your project
- Install all necessary dependencies
- Configure typescript, linter, prettier, etc
- Create a dummy screen with the `Hello world!` text and run it. Check if all works correctly.
- Choose a template, icons, color theme, and APIs (read the next chapter)
- Register and get API keys. Test APIs at their playgrounds or use [Postman](https://www.postman.com/)
- Write a step-by-step plan for your development. **Add a realistic deadline to your calendar!** It will take 2-3 working days to complete this task.
- Start the development, feature-by-feature, commit-by-commit (remember, you need to have a nice commit history!).
- Test your application
- When completed, create an extended `readme.md` file ([example](https://gist.github.com/solaryasha/0fb46a864b490afd618f2c4751a65041), [constructor](https://readme.so/))
- Deploy your project so it can be viewed online (Expo provides you with a great tool to deploy)
- Ask a mentor to give you feedback
- Add project to your portfolio
- Profit!

## Design and API references

Choose one of these free designs:
- [Design #1](https://www.figma.com/file/Aek8A3M8n7eE2jHMQRM4I4/Weather-App-(Uplabs))
- [Design #2](https://www.figma.com/file/GkAQzGJz7htZbeDXflaxln/Weather-App-(Community))
- [Design #3](https://www.figma.com/file/gT7RpnSY3Sd1LMOVn0mJ0M/Weather-Mobile-App-Design-(Community))
- [Design #4](https://uifresh.net/product/weather-forecast-app-ui-template/)
- [Find your own](https://www.google.com/search?q=figma+weather+app+template&source=lnms&tbm=isch&sa=X&ved=2ahUKEwiz-YHAza38AhVE6CoKHRD8BXUQ_AUoAXoECAEQAw&biw=1920&bih=1001&dpr=1)

Choose a free icon pack:
- [Icons #1](https://www.figma.com/file/bulpuHDnPD5GswA7FJgFa1/Weather-Iconset-Frosted-Glass-(Community))
- [Icons #2](https://www.figma.com/file/bLzxGXN9VIz2TQTQB06icM/Weather-icons-(Community))
- [Icons #3](https://www.figma.com/file/VpBA1whOlRtlwHbBkTjpag/Weather-API-Icons-(Community))
- [Icons #4](https://www.figma.com/file/4uahxsgbkXQ2DkLf5jUumt/Degry-Weather-Iconset-(Community))
- [Icons #5](https://www.figma.com/file/UmfL946shSrO3CeJTDu9Va/Weather-Icons---Community-(Community))
- [Icons #6](https://www.figma.com/file/d8tbHTVnbXgaYKqg4UgNhV/Eggciting-Weather-Icons-(Community))
- [Icons #7](https://www.figma.com/file/3stZDcQI19qwLm3kn5YlT1/Weather-Icons-%7C-Flat-%26-Outline-(Community))
- [Icons #8](https://www.figma.com/file/b5ETUPfCLWXekcSeY9MviX/QWeather-Icon-(Community))
- Use icons from API (if provided)

**Don't use original icons from Figma design! Choose one from the list or find yours in Google!**

Additional weather UI icons you can use:
- [Icons set](https://www.figma.com/file/2iWHpUoPS0Cz5EDmjlTeDZ/IconWrap---Weather-%E2%9B%85-(Community)-(Community)-(Community)?node-id=0%3A1&t=GlUnN1gX2dHNcrq2-0)

Generate color theme for your app: [Use palette generator](https://coolors.co/generate)

**Don't use the original Figma template colors! Your app needs to be unique, so use different colors!**

Choose a free weather API:

- [Weather API](https://www.weatherapi.com/)
- [OpenWeatherMap API](https://openweathermap.org/)
- [Open Meteo API](https://open-meteo.com/)

Choose a free location API:

- [Positionstack](https://positionstack.com/)
- [LocationIQ](https://locationiq.com/)

## Features

### Main screen

1. **First run only**. Detect current user location on load. On error - use default (Kyiv, Ukraine).
2. Get user location from the app persistent storage. On error use case #1.
3. Screen consists of the next parts:
  - Header:
    - Logo
    - Update icon (clickable)
    - Settings icon (clickable)
  - Current location (clickable)
  - Current date
  - Current weather:
    - Big icon
    - Short weather description (f.e. `Cloudy`)
    - Current temperature
    - Humidity
    - Wind speed and direction
    - Today’s max and min temperature
    - Precipitation (* optional)
    - Feels like temperature (* optional)
    - Pressure (* optional)
    - ACQI level (* optional)
    - Visibility distance (* optional)
    - Sunrise and sunset time (* optional)
    - Moonphase (* optional)
  - Hourly forecast (horizontally scrollable):
    - Starts from the next full hour, repeats 12 times
    - If the hour belongs to the current day - show the `Today` text
    - If the hour belongs to the next day - show the `Tomorrow` text
    - Icon
    - Temperature
    - Humidity
  - 3-days forecast (or 5, 7 - choose any):
    - Icon
    - Max and min temperature
    - Date
4. Update weather every 5 minutes
5. Update weather on the Update icon click (disable when data is loading, show animation)
6. Open the **Settings screen** on the Settings icon click
7. Open the **Location screen** on Current location click

### Location screen

1. Show the input where the user can type a location
2. Show the back button so the user can return to the **Main screen**
3. Use debounce or add a submit button to call API (to minimize requests count)
4. Show a list of location suggestions from the API
5. Show the current device geolocation option as the first item in the list (if available)
6. After the user selects the location save it to persistent storage and return to the **Main screen**. Update weather and forecast.

### Settings screen

1. Show the next app settings:
  - Temperature: Celsius or Fahrenheit
  - Wind speed: Km/h, m/s, Mph ... (depends on API)
  - Pressure: Hg, bar ... (depends on API)
  - Precipitation: mm, inches ... (depends on API)
  - Language (* optional, depends on API)
2. On option change save it to persistent storage immediately (no need to confirm)
3. On the back button click return to the **Main screen**. If settings have been changed - update the forecast.
