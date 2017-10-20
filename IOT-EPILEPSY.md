# Leveraging AWS Services for Analyzing, Predicting and Actioning on Medical Problems

## Description/Abstract: 

The last few years have seen the number of consumer wearable devices that are available on the market increase significantly. These can range from watches that measure heart rate to even wearable devices that can detect brainwave activity.

Epilepsy is a group of neurological disorders characterized by epileptic seizures. Epileptic seizures are episodes that can vary from brief and nearly undetectable to long periods of vigorous shaking. These episodes can result in physical injuries including occasionally broken bones. In order to diagnose and continue treatment of epilepsy, neurologists use a test called an electroencephalogram (EEG), which is a test that detects electrical activity in your brain using small, flat metal discs (electrodes) attached to your scalp. Your brain cells communicate via electrical impulses and are active all the time, even when you're asleep. In the past, EEGs had to be done in highly controlled environments in a clinic or hospital, but we are now seeing wearable devices that can be used to chart brainwave activity at any time or place.

By using a wearable EEG headset and capturing the data output from these devices, we are able to send them up in near realtime to AWS. The objective is to then analyse the data and predict when medical problems occur so that actions and alerts can be performed. Using Kinesis Firehose, we can obtain a live feed of raw data of 14 channels of brainwave data. When a seizure occurs, an IoT button is pushed which then triggers a Lambda function to archive the data into DynamoDB. The objective is to find a brainwave pattern for each patient which can signal the onset of a seizure. Once a patient’s “seizure signature” is captured, we can then start firing SNS notifications when the Firehose data seems to match the pattern of a seizure.

## Notes: 

Epilesy sufferers incur numerous physical injuries due to their seizures. By using a device like the Emotiv Epoc+ - https://www.emotiv.com/epoc/ , we are now able to capture brainwave activity in realtime. While other brands of EEG headsets do measure brainwave activity, the Emotiv+ measures 14 channels of brainwave activity and allows us to dump the raw data out. By combining this with a Raspberry PI 3, we effectively have a wearable device that can push brainwave data in realtime up to AWS.

Hardware Required Per Patient:
-          Emotiv Epoc+ EEG Headset
-          IoT Button on a lanyard, hanging on the patient’s neck
-          Raspberry PI 3 with the Adafruit Ultimate GPS breakout board
-          Portable battery pack, at least 10,000 mAH

The first step for each patient is to establish a brainwave pattern for seizures. As the 14 channels of brainwave data is being pushed in realtime to Kinesis Firehose, this data can either be discarded or archived based on whether the neurologist wants to perform a long-term analysis on the patient. Once the patient has had a seizure, the IoT button is pressed. This triggers a Lambda function to archive the last 10 minutes of brainwave activity for the neurologist to analyse.

Once the patient’s “seizure pattern” has been established, the incoming data can be continually analysed for patterns and if a seizure pattern is predicted, notifications can be sent via SNS. This can include sending of push notifications to family members or persons physically near the patient so that first aid measures can be performed (with the GPS board on the Raspberry PI, the patient’s location can be sent out as part of the SNS notification). In most seizures, the immediate threat is physical injury or drowning (if near water), so having this notification can be life-saving.


 
