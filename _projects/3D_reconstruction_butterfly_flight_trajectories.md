---
layout: subpage
permalink: /portfolio/3D_reconstruction_butterfly_flight_trajectories/
title: "3D reconstruction of butterfly flight trajectories in semi-natural settings"
---

<div class="container" style="padding-top: 50px; padding-bottom: 80px; max-width: 900px;">

<p style="font-size: 0.9em; margin-bottom: 30px; font-family: 'Montserrat', sans-serif;">
  <a href="{{ site.baseurl }}/portfolio/" style="color: #111827; text-decoration: none; font-weight: 600;">← Back to Portfolio</a>
</p>

<!-- Project Title (Lowered, Natural Casing, No Underline) -->
<h1 style="font-family: 'Montserrat', sans-serif; font-size: 2.2em; font-weight: 700; color: #111827; margin-top: 30px; margin-bottom: 25px; text-transform: none !important;">
  3D reconstruction of butterfly flight trajectories in semi-natural settings
</h1>

<p style="font-family: 'Montserrat', sans-serif; color: #4b5563; font-size: 1.1em; line-height: 1.7; margin-bottom: 40px;">
  Below, I present the key steps of the workflow behind 3D reconstruction, using the quantification of <em>Morpho</em> butterfly flight as an example project.
</p>

<h2 style="font-family: 'Montserrat', sans-serif; color: #111827; margin-top: 40px; margin-bottom: 20px; font-weight: 700; font-size: 1.5em; text-transform: none !important;">Recording Free-Flying Butterflies</h2>

<div style="display: flex; align-items: center; gap: 30px; margin-top: 20px; margin-bottom: 30px; flex-wrap: wrap;">
  <p style="font-family: 'Montserrat', sans-serif; color: #4b5563; font-size: 1.1em; line-height: 1.7; flex: 1; min-width: 280px; margin-bottom: 0;">
    To study butterfly flight, I built an "insect flight studio” in the middle of the Amazon rainforest. It was a 9‑meter long outdoor tunnel, where wild butterflies could fly freely, equipped with a stereoscopic motion capture system: three synchronized high-speed cameras filming at 240 frames per second.
  </p>
  <img src="{{ site.baseurl }}/img/flight cage tarapoto.png" alt="Flight cage tarapoto" style="border-radius: 8px; width: 100%; max-width: 300px; object-fit: contain; box-shadow: 0 4px 12px rgba(0,0,0,0.08);">
</div>

<p style="font-family: 'Montserrat', sans-serif; color: #4b5563; font-size: 1.1em; line-height: 1.7; margin-bottom: 20px;">
Here is an example of the flight trajectory of a <em>Morpho</em> butterfly filmed from both a side and a top view. 
</p>

<div style="margin-top: 20px; margin-bottom: 30px; text-align: center;">
  <img src="{{ site.baseurl }}/img/side and top view menelaus flight GIF.gif" alt="Side and top view flight" style="border-radius: 8px; width: 100%; max-width: 650px; object-fit: contain; box-shadow: 0 4px 12px rgba(0,0,0,0.08);">
</div>

<p style="font-family: 'Montserrat', sans-serif; color: #4b5563; font-size: 1.1em; line-height: 1.7; margin-bottom: 40px;">
Three-dimensional reconstruction works by filming the same scene from multiple viewpoints and then combining those views. The more viewpoints used, the more precise the reconstruction becomes.
</p>

<h2 style="font-family: 'Montserrat', sans-serif; color: #111827; margin-top: 40px; margin-bottom: 20px; font-weight: 700; font-size: 1.5em; text-transform: none !important;">From Video to 3D Motion</h2>

<p style="font-family: 'Montserrat', sans-serif; color: #4b5563; font-size: 1.1em; line-height: 1.7; margin-bottom: 20px;">
A critical step in obtaining 3D information from multiple 2D videos is calibration. Before recording any flight, the three high-speed cameras need to be accurately calibrated so that even a tiny insect’s wing, moving faster than the human eye can see, appears in exactly the right 3D place for each frame.
<br><br>
To achieve this, I used a calibration wand, moving it throughout the recording area much like a majorette twirling a baton. The extremities of the wand were tracked in each camera view to capture the spatial positions of a known-length object. While other calibration devices can also be used, the wand method is highly adaptable to virtually any space.
</p>

<div style="margin-top: 20px; margin-bottom: 30px; text-align: center;">
  <img src="{{ site.baseurl }}/img/wand calibration large cage GIF.gif" alt="Wand calibration" style="border-radius: 8px; width: 100%; max-width: 750px; object-fit: contain; box-shadow: 0 4px 12px rgba(0,0,0,0.08);">
</div>

<p style="font-family: 'Montserrat', sans-serif; color: #4b5563; font-size: 1.1em; line-height: 1.7; margin-bottom: 20px;">
  Using a method called 
  <a href="http://www.kwon3d.com/theory/dlt/dlt.html" target="_blank" style="color: #35594F; font-weight: 600;">Direct Linear Transformation (DLT)</a>
  along with the recorded wand movements, 2D pixel coordinates can be converted into 3D positions for any object passing through the calibrated space.<br><br>
  Here is the reconstructed flight trajectory for the flight sequence shown earlier.
</p>

<div style="margin-top: 20px; margin-bottom: 40px; text-align: center;">
  <img src="{{ site.baseurl }}/img/example reconstructed trajectory.png" alt="Reconstructed trajectory" style="border-radius: 8px; width: 100%; max-width: 700px; object-fit: contain;">
</div>


<h2 style="font-family: 'Montserrat', sans-serif; color: #111827; margin-top: 40px; margin-bottom: 20px; font-weight: 700; font-size: 1.5em; text-transform: none !important;">Extracting Meaningful Flight Metrics</h2>

<p style="font-family: 'Montserrat', sans-serif; color: #4b5563; font-size: 1.1em; line-height: 1.7; margin-bottom: 40px;">
  Once the 3D flight paths were reconstructed, I processed them to turn raw coordinates into interpretable performance and behavioral metrics. 
  For example, I could investigate differences in flight behavior among species using measures of sinuosity, flight speed, acceleration, or average flight height. 
  I also evaluated critical performance metrics such as gliding efficiency by computing the glide angle during gliding flight phases.
  <br><br>
  <span>
    The data processing and analysis pipeline is implemented in R and openly available on
    <a href="https://github.com/Camille-Le-Roy/flight_data_analysis" 
       target="_blank" 
       style="color: #35594F; text-decoration: none; font-weight: 700;">
      GitHub
    </a>.
  </span>
</p>


<h2 style="font-family: 'Montserrat', sans-serif; color: #111827; margin-top: 40px; margin-bottom: 20px; font-weight: 700; font-size: 1.5em; text-transform: none !important;">Softwares</h2>

<div style="font-family: 'Montserrat', sans-serif; color: #4b5563; font-size: 1.1em; line-height: 1.7; margin-bottom: 40px;">
  <ul style="list-style-type: disc; padding-left: 20px; margin: 0;">
    <li style="margin-bottom: 10px;">
      <strong><a href="https://biomech.web.unc.edu/dltdv/" target="_blank" style="color: #35594F; text-decoration: none; font-weight: 700">DLTdv</a>:</strong>
      A MATLAB-based digitizing tool designed specifically for 3D reconstruction.
    </li>
    <li style="margin-bottom: 10px;">
      <strong><a href="https://biomech.web.unc.edu/wand-calibration-tools/" target="_blank" style="color: #35594F; text-decoration: none; font-weight: 700">easyWand</a>:</strong>
      A companion tool to DLTdv for calibrating camera setups using the wand method.
    </li>
    <li>
      <strong><a href="https://deeplabcut.github.io/DeepLabCut/README.html" target="_blank" style="color: #35594F; text-decoration: none; font-weight: 700">DeepLabCut</a>:</strong>
      A Python library for pose estimation, allowing you to fine-tune deep neural networks for automatic tracking of your object of interest.
    </li>
  </ul>
</div>

<h2 style="font-family: 'Montserrat', sans-serif; color: #111827; margin-top: 40px; margin-bottom: 20px; font-weight: 700; font-size: 1.5em; text-transform: none !important;">Applications</h2>

<p style="font-family: 'Montserrat', sans-serif; color: #4b5563; font-size: 1.1em; line-height: 1.7; margin-bottom: 40px;">
  I've used three-dimensional reconstruction approaches to investigate insect flight in diverse contexts, from examining how wing damage affects performance, to studying how microhabitat specialization shapes flight behavior, and even uncovering the dynamics of sexual flight interactions. You can find more about these studies on my <a href="{{ site.baseurl }}/publications" style="color: #35594F; text-decoration: none; font-weight: 700">Publications page</a>.
</p>

<p style="font-size: 0.9em; margin-top: 4em; font-family: 'Montserrat', sans-serif;">
  <a href="{{ site.baseurl }}/portfolio/" style="color: #111827; text-decoration: none; font-weight: 600;">← Back to Portfolio</a>
</p>

</div>