---
layout: page
title: About HeartWear
modified: 2015-09-26
excerpt: "Why HeartWear has a major impact on population health."
image:
  feature: hwbanner3.png
  credit: Lexie & RRC
---


<figure>
	<img src="/images/concept_map1.png">
</figure>

## Getting the Heart Rate Data

With HeartWear, the application harnesses the input data from a wearable heartrate monitoring API.  In this case, a [Fitbit Charge HR](https://www.fitbit.com/chargehr) or a [Moto 360](https://www.motorola.com/us/products/moto-360).

---

## Loading in the Cloud

With Google Cloud Messaging, the user variables of interest from the JSON queries include number of steps, heart rate, and quality of sleep indicators such as total sleep and number of times restress.

---

## Classifying a Emergency Event

In the clinical literature, there are few predictors of a tachycardiac event other than age and gender.  However, variability in the patient's heart rate pattern in a 15 to 30 minute period prior to a emergency tachycardiac event has been identified in clinical trials.  
<br>
Therefore, to train a statistical clinical heart rate classifer, we exported Apple Health heart rate and activity data plotted heart rate vs activity graph in order to predict said variability in the patient's heart rate pattern with a support vector machine with Python's [Sci-Kit Learn](http://scikit-learn.org/stable/).
<br>

---

## Preventing False Positives

In precision medicine, each patient biologically presents at varying resting heart rates at varying levels of quality of life.



---

## Notifications

In the event of a impending cardiac emergency, such as tachycardia, the patient's designated emergency contact will receive the following push notification through Google Cloud Messaging:

> Your registered contact is having a cardiac event.  Please dial 9-1-1 immediately.

---

## Continuous Monitoring Care, Instant Updates

The HeartWear app comes with a wigit for continuous monitoring.  Synced every hour, if the patient's heart rate is normal level then the wigit will show a <font color = "green">green</font> heart, such as normal resting pulse of 80 beats per minute (BPM).  
<br>
If the patient's heart rate is elevated 120 BPM, then the wigit will change color to <font color = "goldenrod">yellow</font> as a warning indicator.
Finally, if the patient's heart rate is elevated to 180 BPM or above, then the wigit logo when synced changes color to <font color = "red">red</font>.

<figure class="half">
	<img src="/images/hearts.png">
</figure>

Should the emergency contact want an ongoing update




---
<br>
**References.**  

<small>
Porter, Michael J., et al. "Influence of age and gender on the mechanism of supraventricular tachycardia." Heart Rhythm 1.4 (2004): 393-396.
</small>
<br>
<small>
Stein, Phyllis K., et al. "Development of more erratic heart rate patterns is associated with mortality post–myocardial infarction." Journal of electrocardiology 41.2 (2008): 110-115.
</small>
<br>
<small>
Acharya, U. Rajendra, et al. "Classification of heart rate data using artificial neural network and fuzzy equivalence relation." Pattern Recognition 36.1 (2003): 61-68.
</small>


