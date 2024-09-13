---
title: Analytics Dashboard
publishDate: 2024-01-01
img: /assets/dashboard.PNG
img_alt: Overview of the predictive analytics dashboard
description: |
  Developed a comprehensive predictive analytics dashboard to identify factors leading to customer churn and forecast future revenue.

  The dashboard provided actionable insights for strategic decision-making, helping to reduce churn and improve financial forecasting.
tags:
  - Data Analysis
  - Machine Learning
  - Power BI
  - Predictive Analytics
---

## Project Overview

### Data Cleaning

Performed extensive data cleaning to prepare the dataset for analysis. This involved:

- Removing duplicates and irrelevant data
- Handling missing values
- Standardizing data formats

### Dashboard Creation

Created an interactive and dynamic dashboard using Power BI to visualize:

- Key financial metrics
- Factors contributing to customer churn
- Forecasted revenue and future contract signings

### Automation

Developed automated scripts for:

- Data cleaning processes to reduce manual effort
- Predictive modeling to provide real-time insights

### Predictive Analysis

Applied machine learning techniques to:

- Identify factors influencing customer churn
- Forecast future revenue and contract signings

## Screenshots

<!-- Slideshow for Dashboard Overview section -->
<div id="dashboard-overview-slideshow" style="display: flex; align-items: center;">
  <img id="dashboard-slideshow-img" src="/assets/1.PNG" alt="Dashboard Overview" style="width: 50%; margin-right: 1rem; cursor: pointer;" onclick="openModal(0, 'dashboard')" />
  <p><strong>Dashboard Overview</strong>: An overview of the dashboard displaying key metrics and visualizations.</p>
</div>

<!-- Static images with zoom functionality for Churn and Forecasting sections -->
<div style="display: flex; align-items: center;">
  <img src="/assets/churn.PNG" alt="Churn Factors Analysis" style="width: 50%; margin-right: 1rem; cursor: pointer;" onclick="openModal(0, 'churn')" />
  <p><strong>Churn Factors Analysis</strong>: Visualization of factors contributing to customer churn.</p>
</div>

<div style="display: flex; align-items: center;">
  <img src="/assets/forcasting.PNG" alt="Revenue Forecasting" style="width: 50%; margin-right: 1rem; cursor: pointer;" onclick="openModal(0, 'forecasting')" />
  <p><strong>Revenue Forecasting</strong>: Forecasting of future revenue and contract signings.</p>
</div>

<!-- Modal for enlarged view of images -->
<div id="modal" style="display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background-color: rgba(0,0,0,0.8); justify-content: center; align-items: center;">
  <span style="position: absolute; top: 10px; right: 20px; font-size: 2rem; color: white; cursor: pointer;" onclick="closeModal()">&times;</span>
  <button style="position: absolute; left: 10px; top: 50%; font-size: 2rem; color: white; background: none; border: none; cursor: pointer;" onclick="prevImage()">&lt;</button>
  <img id="modal-img" src="" alt="Expanded View" style="max-width: 90%; max-height: 90%;" />
  <button style="position: absolute; right: 10px; top: 50%; font-size: 2rem; color: white; background: none; border: none; cursor: pointer;" onclick="nextImage()">&gt;</button>
</div>

<script>
  const dashboardImages = [
    '/assets/1.PNG',
    '/assets/2.PNG',
    '/assets/3.PNG',
    '/assets/4.PNG'
  ];

  let currentIndex = 0;
  let slideshowInterval;

  function updateSlideshow() {
    document.getElementById('dashboard-slideshow-img').src = dashboardImages[currentIndex];
  }

  function startSlideshow() {
    slideshowInterval = setInterval(() => {
      currentIndex = (currentIndex + 1) % dashboardImages.length;
      updateSlideshow();
      if (document.getElementById('modal').style.display === 'flex' && modalType === 'dashboard') {
        document.getElementById('modal-img').src = dashboardImages[currentIndex];
      }
    }, 3000); // Change image every 3 seconds
  }

  let modalType = '';

  function openModal(index, type) {
    currentIndex = index;
    modalType = type;

    if (type === 'dashboard') {
      document.getElementById('modal-img').src = dashboardImages[currentIndex];
      document.getElementById('modal').style.display = 'flex';
      clearInterval(slideshowInterval); // Stop previous interval to prevent multiple intervals
      startSlideshow(); // Restart slideshow with modal
    } else {
      let imgSrc = type === 'churn' ? '/assets/churn.PNG' : '/assets/forcasting.PNG';
      document.getElementById('modal-img').src = imgSrc;
      document.getElementById('modal').style.display = 'flex';
      clearInterval(slideshowInterval); // Ensure the slideshow stops for non-dashboard images
    }
  }

  function closeModal() {
    document.getElementById('modal').style.display = 'none';
    if (modalType === 'dashboard') {
      clearInterval(slideshowInterval); // Stop slideshow when modal is closed
      startSlideshow(); // Restart slideshow for normal view
    }
  }

  function prevImage() {
    if (modalType === 'dashboard') {
      currentIndex = (currentIndex > 0) ? currentIndex - 1 : dashboardImages.length - 1;
      document.getElementById('modal-img').src = dashboardImages[currentIndex];
    }
  }

  function nextImage() {
    if (modalType === 'dashboard') {
      currentIndex = (currentIndex < dashboardImages.length - 1) ? currentIndex + 1 : 0;
      document.getElementById('modal-img').src = dashboardImages[currentIndex];
    }
  }

  // Start the slideshow when the page loads
  window.onload = startSlideshow;
</script>
