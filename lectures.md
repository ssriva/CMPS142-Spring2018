---
layout: default
title: Lectures
active_tab: lectures
---

<!-- Create a HTML anchor for the most recent lecture -->
{% assign anchor_created = false %}
{% capture now %}{{'now' | date: '%s'}}{% endcapture %}
<!-- End create a HTML anchor for the most recent lecture -->

Here is a tentative syllabus for the Machine Learning class. Expect this to change significantly, especially during the first few weeks into the quarter. Also, it is unlikely that we will get to everything on this list.
* Introduction and overview of machine learning and key concepts,
* Supervised learning:
* Linear regression
* Regularization and Bias-Variance tradeoff 
* Logistic regression 
* Probability review
* Generative learning models, Naive Bayes 
* Perceptron Algorithm
* Support Vector Machines 
* Decision Trees
* Neural networks
* Model selection and feature selection
* Ensemble Methods 
* Multi-class classification
* Unsupervised learning (clustering, Mixture of Gaussians)
* On-line learning


The lecture schedule will be updated as the term progresses. 

<table class="table table-striped">
  <thead>
    <tr>
      <th>Date</th> 
      <th>Topic</th>
      <th>Readings</th>
      <th>Announcements</th>
    </tr>
  </thead>
  <tbody>
    {% for lecture in site.data.lectures %}

    <!-- Create a HTML anchor for the most recent lecture -->
    {% capture lecture_date %}{{lecture.date | date: '%s'}}{% endcapture %}
    {% assign lecture_date = lecture_date | plus: 0 %}
    {% assign now = now | minus: 14400 %}

    <tr
    {% if anchor_created != true and lecture_date >= now %}
      {% assign anchor_created = true %}
      id="now" 
    {% endif %}
    
    {% if lecture.type %}
      {% if lecture.type and lecture.type == 'exam' %}
        class="info" 
      {% else if lecture.type and lecture.type == 'deadline' %}
        class="warning"
      {% else if lecture.type and lecture.type == 'no_lecture' %}
        class="success"
      {% endif %}
    {% endif %}
    >

    <!-- End create a HTML anchor for the most recent lecture -->
      <td>{{ lecture.date | date: '%a, %b %-d, %Y' }}</td>
      <td>
        {% if lecture.slides %}
          <a href="{{ lecture.slides }}">{{ lecture.title }}</a>
        {% else %}
         {{ lecture.title }} 
        {% endif %}



	    {% if lecture.speaker %}
          {% if lecture.speaker_url %}
            by <a href="{{ lecture.speaker_url }}">{{ lecture.speaker }}</a> 
          {% else %} 
          by {{ lecture.speaker }}
          {% endif %}
	    {% endif %}

      </td>
      <td>
        {% if lecture.readings %} 
          {% for reading in lecture.readings %}
          {% if reading.url %}
              {% if reading.optional %}<b>Optional:</b> {% endif %}
              {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a> 
            <br />
          {% else %}
              {% if reading.optional %}<b>Optional</b> {% endif %}
             {{ reading.authors }}, {{ reading.title }} 
            <br />
          {% endif %}
          {% endfor %}
        {% endif %}
      </td>
       <td>
        {% if lecture.videos %} 
          {% for video in lecture.videos %}
          {% if video.authors %} {{ video.authors }}, {% endif %}
	  <a href="{{ video.url }}">{{ video.title }}</a> 
          {% if video.length %} ({{ video.length }}) {% endif %}
            <br />
          {% endfor %}
        {% endif %}
      </td>
    </tr>
    {% endfor %}
    
  </tbody>
</table>

