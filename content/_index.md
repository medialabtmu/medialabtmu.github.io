---
title: "TMU Multimedia Research Laboratory"
date: 2024-01-01
type: landing


# Homepage sections
sections:
  - block: carousel
    content:
      images:
        - photo1.jpg
        - photo2.jpg
        - photo3.jpg
      interval: 5000

  - block: hero
    content:
      title: TMU Multimedia Research Laboratory
      text: |
        The TMU Multimedia Research Laboratory is an internationally recognized
        engineering lab at Toronto Metropolitan University. We focus on three
        key research areas: multimedia signal processing, computer vision, and
        machine learning.
      primary_action:
        text: Join Us
        url: /join/
      secondary_action:
        text: View Projects
        url: /projects/
    design:
      no_padding: true
      css_class: "py-12 sm:py-16"

  - block: features
    content:
      title: Research Areas
      items:
        - name: Multimedia
         
          description: |
            Signal and image processing, information fusion, affective computing.
        - name: Computer Vision
         
          description: |
            Object recognition and tracking, action recognition, virtual/augmented reality, medical imaging.
        - name: Machine Learning
          
          description: |
            Deep learning, multimodal learning, generative AI.

  - block: collection
    content:
      title: Latest News
      subtitle: ""
      text: ""
      count: 5
      filters:
        folders:
          - news
        author: ""
        category: ""
        tag: ""
    design:
      view: article
      columns: 2

  - block: collection
    content:
      title: Recent Publications
      subtitle: ""
      text: ""
      count: 5
      filters:
        folders:
          - publications
    design:
      view: article
---
