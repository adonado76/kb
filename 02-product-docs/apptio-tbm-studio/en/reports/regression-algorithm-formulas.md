---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Regression algorithm formulas"
breadcrumb: []
source_path: "reports/regression-algorithm-formulas.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Regression algorithm formulas

Applies to: TBM Studio 12.0 and later

A useful feature of trend charts is the ability to add projections to the charts. The application
offers a range of regression algorithms that can be applied to projections. The algorithms are:

- Regression
- Multiple Linear Regression
- Polynomial Regression
- Simple Exponential Smoothing
- Double Exponential Smoothing
- Moving Average

The application algorithms are based on standard Java OpenForecast regression algorithms. The
descriptions below are taken from Java documentation: [OpenForecast](http://openforecast.sourceforge.net/docs/) "(Opens in a new tab or window)").

## Regression

Implements a single variable linear regression model. A single variable linear regression model
essentially attempts to put a straight line through the data points. This line is defined by its
gradient or slope, and the point at which it intercepts the x-axis (i.e. where the independent
variable has, perhaps only theoretically, a value of zero). Mathematically, assuming the independent
variable is x and the dependent variable is y, then this line can be represented as:

> ```
> y = intercept +
>           slope * x
> ```

## Multiple linear regression

Implements a multiple variable linear regression model. A multiple variable linear regression
model essentially attempts to put a hyperplane through the data points. Mathematically, assuming the
independent variables are xi and the dependent variable is y, then this hyperplane can be
represented as:

> ```
> y = a0 + a1*x1 +
>           a2*x2 + a3*x3 +
> ```

...where the ai are the coefficients of the regression. The coefficient a0 is also referred to as
the intercept. If all xi were zero (theoretically at least), it is the forecast value of the
dependentVariable, y.

## Polynomial regression

Implements a single variable polynomial regression model. A single variable polynomial regression
model essentially attempts to put a polynomial line (a curve if you prefer) through the data points.
Mathematically, assuming the independent variable is x and the dependent variable is y, then this
line can be represented as:

> ```
> y = a0 + a1*x +
>           a2*x2 + a3*x3 + ... + am*xm
> ```

## Simple exponential smoothing

A simple exponential smoothing forecast model is a very popular model used to produce a smoothed
Time Series. Whereas in simple Moving Average models the past observations are weighted equally,
Exponential Smoothing assigns exponentially decreasing weights as the observations get older.

In other words, recent observations are given relatively more weight in forecasting than the
older observations.

In the case of moving averages, the weights assigned to the observations are the same and are
equal to 1/N. In simple exponential smoothing, however, a smoothing parameter or smoothing constant
is used to determine the weights assigned to the observations.

This simple exponential smoothing model begins by setting the forecast for the second period
equal to the observation of the first period.

## Double exponential smoothing

Double exponential smoothing (also known as Holt exponential smoothing) is a refinement of the
popular simple exponential smoothing model but adds another component, which takes into account any
trend in the data. Simple exponential smoothing models work best with data where there are no trend
or seasonality components to the data. When the data exhibits either an increasing or decreasing
trend over time, simple exponential smoothing forecasts tend to lag behind observations. Double
exponential smoothing is designed to address this type of data series by taking into account any
trend in the data.

Note that double exponential smoothing still does not address seasonality. For better
exponentially smoothed forecasts using data where there is expected or known to be seasonal
variation in the data, use triple exponential smoothing.

As with simple exponential smoothing, in double exponential smoothing models, past observations
are given exponentially smaller weights as the observations get older. In other words, recent
observations are given relatively more weight in forecasting than the older observations.

There are two equations associated with Double Exponential Smoothing:

> ```
> ft =
>           a.Yt+(1-a)(ft-1+bt-1)
> ```
>
> `bt = g.(ft-ft-1)+(1-g).bt-1`

where:

- Yt is the observed value at time t.
- ft is the forecast at time t.
- bt is the estimated slope at time t.
- a, representing alpha, is the first smoothing constant, used to smooth the observations.
- g, representing gamma, is the second smoothing constant, used to smooth the trend.

To initialize the double exponential smoothing model, f1 is set to Y1, and the initial slope b1
is set to the difference between the first two observations; i.e. Y2-Y1.

## Triple exponential smoothing

Triple exponential smoothing (also known as the Winters method) is a refinement of the popular
double exponential smoothing model but adds another component which takes into account any
seasonality (or periodicity) in the data.

Simple exponential smoothing models work best with data where there are no trend or seasonality
components to the data. When the data exhibits either an increasing or decreasing trend over time,
simple exponential smoothing forecasts tend to lag behind observations. Double exponential smoothing
is designed to address this type of data series by taking into account any trend in the data.
However, neither of these exponential smoothing models address any seasonality in the data.

For better exponentially smoothed forecasts of data where there is expected or known to be
seasonal variation in the data, use triple exponential smoothing.

As with simple exponential smoothing, in triple exponential smoothing models, past observations
are given exponentially smaller weights as the observations get older. In other words, recent
observations are given relatively more weight in forecasting than the older observations. This is
true for all terms involved. Namely, the base level Lt, the trend Tt, as well as the seasonality
index st.

There are four equations associated with Triple Exponential Smoothing:

> ```
> Lt =
>           a.(xt/st-c)+(1-a).(Lt-1+Tt-1)
> ```
>
> ```
> Tt = b.(Lt-Lt-1)+(1-b).Tt-1
> st =
>           g.(xt/Lt)+(1-g).st-c
> ```
>
> `ft,k = (Lt+k.Tt).st+k-c`

where:

- Lt is the estimate of the base value at time t. That is, the estimate for time t after
  eliminating the effects of seasonality and trend.
- a, representing alpha, is the first smoothing constant, used to smooth Lt.
- xt is the observed value at time t.
- st is the seasonal index at time t.
- c is the number of periods in the seasonal pattern. For example, c=4 for quarterly data, or c=12
  for monthly data.
- Tt is the estimated trend at time t.
- b, representing beta, is the second smoothing constant, used to smooth the trend estimates.
- g, representing gamma, is the third smoothing constant, used to smooth the seasonality
  estimates.
- ft,k is the forecast at time the end of period t for the period t+k.

There are a variety of ways to come up with initial values for the triple exponential smoothing
model. The approach implemented here uses the first two years (or complete cycles) of data to come
up with initial values for Lt, Tt and st. Therefore, at least two complete cycles of data are
required to initialize the model. For the best results, more data is recommended (ideally a minimum
of 4 or 5 complete cycles). This gives the model a chance to better adapt to the data, instead of
relying on getting (guessing) good estimates for the initial conditions.

## Moving average

A moving average forecast model is based on an artificially constructed time series in which the
value for a given time period is replaced by the mean of that value and the values for some number
of preceding and succeeding time periods. As you may have guessed from the description, this model
is best suited to time-series data; i.e. data that changes over time.

Since the forecast value for any given period is an average of the previous periods, then the
forecast will always appear to lag behind either increases or decreases in the observed (dependent)
values. For example, if a data series has a noticeable upward trend then a moving average forecast
will generally provide an underestimate of the values of the dependent variable.

The moving average method has an advantage over other forecasting models in that it does smooth
out peaks and troughs (or valleys) in a set of observations. However, it also has several
disadvantages. In particular, this model does not produce an actual equation. Therefore, it is not
all that useful as a medium-long range forecasting tool. It can only reliably be used to forecast
one or two periods into the future.

The moving average model is a special case of the more general weighted moving average. In the
simple moving average, all weights are equal.
