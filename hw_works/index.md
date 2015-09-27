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

With Google Cloud Messaging and Socket.io, the user variables of interest from the JSON queries include number of steps, heart rate, and quality of sleep indicators such as total sleep and number of times restress.

---

## Classifying a Emergency Event

In the clinical literature, there are few predictors of a tachycardiac event other than age and gender.  However, variability in the patient's heart rate pattern in a 15 to 30 minute period prior to a emergency tachycardiac event has been identified in clinical trials.  
<br>
Therefore, to train a statistical clinical heart rate classifer, we exported Apple Health heart rate and activity data plotted heart rate vs activity graph in order to predict said variability in the patient's heart rate pattern with a  one class support vector machine with Python's [Sci-Kit Learn](http://scikit-learn.org/stable/).  

<figure>
	<img src="/images/svm.png">
</figure>

---

## Preventing False Positives

In precision medicine, each patient biologically presents at varying resting heart rates at varying levels of quality of life.  
<br>
In the event that a patient is exercising or performing a strenuous task that may trigger the HeartWear emergency notification, the patient will receive the following notification on their own phone.

> We have detected abnormal heart rate.  
> Is everything OK?  
> YES or NO

If the patient indicates "NO" or does not respond after 3 minutes, a notification is instantly pushed to the patient's emergency contact.  If the patient indicates "YES", then the "YES" indication is added to the SVM classifier to retrain the model and reduce false positives.  

---

## Notifications

In the event of a impending cardiac emergency, such as tachycardia, the patient's designated emergency contact will receive the following push notification through Google Cloud Messaging:

> Your emergency contact requires medical attention. 

---

## Continuous Monitoring Care, Instant Updates

<figure class="half">
	<img src="/images/hearts.png">
</figure>
<br>
The HeartWear app comes with a widget for continuous monitoring.  Synced every hour, if the patient's heart rate is normal level then the widget will show a <font color = "green">green</font> heart, such as normal resting pulse of 80 beats per minute (BPM).  
<br>
If the patient's heart rate is elevated 120 BPM, then the widget will change color to <font color = "goldenrod">yellow</font> as a warning indicator.  
<br>
Finally, if the patient's heart rate is elevated to 180 BPM or above, then the widget logo when synced changes color to <font color = "red">red</font>.  
<br>
Should the emergency contact want an instant update of their loved one's heart rate status, they can push the HR wigit on their phone for immediate refresh.  
<br>
The emergency contact can have the option of being notified if the patient's heart rate is 'Elevated' for such chronic heart conditions such as Marfan's Syndrome.

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


