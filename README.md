# MADS-694

Milestone Project 2: Close Encounters

A Study of Small Body Trajectories in Our Solar System
By Andre Kleber, Trevor McCalmont & Julien Weinstein

Project Summary

The Jet Propulsion Laboratory out of the California Institute of Technology maintains a Small Body Database (SBDB) containing the orbit and position for all known small bodies in outer space. A Small Body is a natural astronomical object that is not a planet or satellite. This usually means all asteroids and comets, but can also include dwarf planets. For our purposes, these bodies are of interest because of a potential collision between a small body and planet Earth. By tracking their orbits and positions, we can study past trajectories and predict future paths of near-Earth objects through the solar system, and assess the risk of our paths crossing. Therefore, we will leverage the SBDB to acquire a large dataset of asteroid trajectories and use its features to generate models that predict the likelihood of a close-approach with Earth.

The SBDB API allows users to submit queries that return asteroid datasets according to the chosen parameters, which include date ranges for the query ranging from as early as January 1, 1900 up through January 1, 2100, and a maximum distance specification which includes only asteroids that have come within that distance of Earth. Based on the query, the API returns important features of each asteroid  such as its diameter (km), velocity (m/s), absolute magnitude (which is an astronomical term for the luminosity of the body), distance from the earth at closest approach (km), the year, day, and time of this approach, and the 3-sigma uncertainty in some of these values.

For this study, we conducted a query for all asteroids that have or will approach within 0.2 astronomical units (au), or about 30 million kilometers, from Earth. For reference, the moon is about 385,000 kilometers from Earth. The query includes all aforementioned parameters, as well as the min/max and uncertainty in each numerical variable. For example, the distance metric includes a min/max estimate of 3 standard deviations in each direction, and the velocity metric includes a relative and infinite velocity, which is the velocity relative to a massless body. There is also a column for the uncertainty in diameter and in time of closest approach.Taken together, there are nine informative features for each asteroid. The query was executed in a Google CoLab notebook using the Python requests library. There were 147,577 records returned by the query.

We used the features of small bodies to predict whether they will be a Potentially Hazardous Asteroid (PHA), defined as coming within 0.05 AU of Earth, or about 4.5 million miles, and having an absolute magnitude of less than 22 units. Absolute magnitude measures the luminosity of celestial objects. An object's absolute magnitude is equal to the apparent magnitude that the object would have if it were viewed from a distance of exactly 10 parsecs (32.6 light-years). By hypothetically placing all objects at a standard reference distance from the observer, their luminosities can be directly compared among each other on a magnitude scale.

We also used unsupervised learning methods to attempt to discover structure in unlabeled data. We primarily looked at clustering methods among the asteroid attributes and whether there are outliers and anomalies that could lead us to some meaningful insights.
