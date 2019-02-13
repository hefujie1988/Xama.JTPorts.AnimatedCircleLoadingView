# Xamarin Animated Circle Loading View
[![platform](https://img.shields.io/badge/platform-Xamarin.Android-brightgreen.svg)](https://www.xamarin.com/)
[![API](https://img.shields.io/badge/API-10%2B-orange.svg?style=flat)](https://android-arsenal.com/api?level=10s)

C# Port of the Android Java library [AnimatedCircleLoadingView](https://github.com/jlmd/AnimatedCircleLoadingView) by [jlmd](https://github.com/jlmd)

### Namespace: Xama.JTPorts.AnimatedCircleLoadingView

## Outstanding Tasks:

- [x] Ensure Interfaces are implemented as per OOP standards.

- [x] Apply standard capitalizations across the library as per .Net guidelines.

- [ ] Fix xml attributes

- [ ] Replace android 'listeners' with events.

- [x] Replace colour implementations to match Xamarin.Android property requirements.

- [ ] Ensure that non-optional parameters are all auto-populated if not supplied for the OO implementation.

- [ ] Check for missing functionality in ported library and task out implementation.

- [ ] Create NuGet package.

- [ ] Set-up Travis-CI and make sure it works against the class library.

- [x] Fill basic usage information.

## Basic Usage:

Create control in your xml layout:

```cs
<Xama.JTPorts.AnimatedCircleLoadingView.AnimatedCircleLoadingView
  android:id="@+id/circle_loading_view_indeterminate"
  android:layout_width="250dp"
  android:layout_height="250dp"
  android:background="@color/white" />
```
### Indeterminate Progress

Get control and assign the colors, **this is important** as currently the control can't infer these if not provided

```cs
AnimatedCircleLoadingView animatedCircleLoadingView = FindViewById<AnimatedCircleLoadingView>(Resource.Id.circle_loading_view_indeterminate);

animatedCircleLoadingView.MainColor = Resource.Color.colorPrimaryDark;
animatedCircleLoadingView.SecondaryColor = Resource.Color.risualOrange;
animatedCircleLoadingView.TextColor = Resource.Color.colorAccent;
animatedCircleLoadingView.CheckMarkTintColor = Color.White;
```

You can define a center body of text to sit inside of the loading view if needed

```cs
animatedCircleLoadingView.TitleText = "Loading";
```
Then simply start the animation

```cs
animatedCircleLoadingView.StartIndeterminate();
```

### Determinate Progress

Get control and assign the colors, this is important as currently the control can't infer these if not provided

```cs
AnimatedCircleLoadingView animatedCircleLoadingView = FindViewById<AnimatedCircleLoadingView>(Resource.Id.circle_loading_view_indeterminate);

animatedCircleLoadingView.MainColor = Resource.Color.colorPrimaryDark;
animatedCircleLoadingView.SecondaryColor = Resource.Color.risualOrange;
animatedCircleLoadingView.TextColor = Resource.Color.colorAccent;
animatedCircleLoadingView.CheckMarkTintColor = Color.White;
```

Start the animation

```cs
animatedCircleLoadingView.StartDeterminate();
```

Then simply set the percentage using this method (takes an integer value)

```cs
animatedCircleLoadingView.SetPercentage(50);
```

Currently when the control hits 100 percent it automatically adds the FinishedOK view, but you can also fire this manually.

```cs
animatedCircleLoadingView.StopOk();
```

or the failed view

```cs
animatedCircleLoadingView.StopFailure();
```
