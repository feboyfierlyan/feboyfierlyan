# JariLingo

An iOS app for learning Indonesian Sign Language (BISINDO), with gesture recognition on the device.

[Full case study](https://feboyfierlyan.com/projects/jarilingo) · [Back to my profile](../README.md)

![Gesture lesson, corrective feedback, and completion screens](../assets/jarilingo.png)

## The problem

Learning a visual language needs more than a vocabulary list. The app gives learners a gesture to practise and feedback from their camera, inside a guided lesson.

## My contribution

I built the iOS MVP and its ML pipeline: landmark extraction, temporal features, model training, Core ML conversion, and the SwiftUI learning flow. The case study documents this as a solo project.

## Engineering decisions

- **Use landmarks as model input.** The pipeline extracts hand geometry instead of classifying whole video frames. It uses position, velocity, and acceleration over a sequence of frames.
- **Keep inference on the device.** A TensorFlow sequence model is converted to Core ML for the iOS app.
- **Coordinate inference with the lesson UI.** Recognition pauses after a correct answer, letting the app transition to feedback. Lightweight SwiftUI effects replace heavier animation work in that flow.

## Scope and evidence

The published case study describes an MVP trained around 32 isolated signs from the WL-BISINDO dataset. This is a constrained learning experience, not a general sign-language translator. Some curriculum content is local demo data.

The screenshots here come from the published portfolio. They show the interface; they are not a performance benchmark. This profile repository contains the showcase; source code and installation packages are not included.

Dataset credit: Grace Oktaviani Kindy, Glenn Leonali, and Henry Lucky, *Word-Level BISINDO: A Novel Video Indonesian Sign Language Dataset and Baseline Methods* (2025). See the [paper](https://doi.org/10.1016/j.procs.2025.08.277) and acknowledgements in the full case study.

**Explore:** [Product screens, implementation journey, and tradeoffs →](https://feboyfierlyan.com/projects/jarilingo)
