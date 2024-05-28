---
layout: project_page
permalink: /

title: "FastNav: A Fine-tuned Adaptive Small-language-model Trained for Multi-point Robot Navigation"
authors:
   Yuxuan Chen$^{1}$, Yixin Han$^{1}$ and Xiao Li$^1$
affiliations:
    $^{1}$ School of Mechanical Engineering, Shanghai Jiao Tong University
paper: https://www.cs.virginia.edu/~robins/Turing_Paper_1936.pdf
video: https://www.youtube.com/results?search_query=turing+machine
code: https://github.com/topics/turing-machines
data: https://huggingface.co/docs/datasets
---

<div style="text-align: center;">
    <img src="/static/image/Figure1.png" alt="Figure1" style="max-width: 100%; height: auto;">
    <p><em>FastNav is a method for compressing large models for robot navigation.</em></p>
</div>
<br><br>

<!-- Using HTML to center the abstract -->
<div class="columns is-centered has-text-centered">
    <div class="column is-four-fifths">
        <h2 style="font-size: 36px;">Abstract</h2>
        <div class="content has-text-justified">
As large language models (LLMs) develop rapidly, robots have started to enjoy the benefits that new control methods with large models bring. Because edge computing meets the requirements of fast response, privacy and network independence, we believe it is beneficial to the widespread of large models applied for robot navigation or even for various industries. In this paper, we propose a method for using lightweight LLMs, also known as small language models (SLMs), for robot navigation, which is called FastNav, a fine-tuned adaptive small-language-model trained for multi-point robot navigation. The proposed method contains three modules, fine-tuning, teacher-student iteration and robot navigation controller. We train and evaluate models with FastNav in both simulation environment and real robot, proving that we can deploy them with low cost but high accuracy and few response time. Compared to other compression methods, FastNav shows its huge potential in local deployment of large models and tends to be a promising solution for multi-point robot navigation.
        </div>
    </div>
</div>
<br>

<div class="columns is-centered has-text-centered">
    <div class="column is-four-fifths">
        <h2 style="font-size: 36px;">Video</h2> 
        <div class="content">
            <video width="100%" height="auto" controls autoplay muted>
                <source src="/static/videos/hospital_frontdesk4X.mp4" type="video/mp4">
                Your browser does not support the video tag.
            </video>
            <p></p>
        </div>
    </div>
</div>
<br>

<br>

## Approach
![Architecture](/static/image/Architecture.png)
### Fine-tuning
Fine-tuning is a crucial technique for adapting Small Language Models (SLMs) to specific tasks, such as robot navigation. To address this, Parameter-Efficient Fine Tuning (PEFT) methods like LoRA (Low-Rank Adaptation) are employed. LoRA updates only a small subset of parameters, significantly reducing training costs while maintaining performance. Fine-tuning enables SLMs to generate task-specific outputs, such as JSON-formatted navigation instructions and reasoning explanations, making them highly effective for domain-specific applications.

### Teacher-student Iteration
The teacher-student iteration method involves a knowledgeable teacher model, such as GPT-4, guiding a less knowledgeable student model, a fine-tuned SLM. The teacher generates prompts based on task requirements and environmental information, adjusting these prompts iteratively based on feedback from the student's performance. The student then attempts the task, and its output is used to inform the next round of prompts. This iterative process continues, refining the student's capabilities and improving task performance through continuous feedback and adjustment.

### Robot Navigation Controller
The robot navigation controller uses the Gmapping algorithm to dynamically map the environment and direct the robot towards specified goal points. This helps the robot precisely navigate to specified goal points while automatically avoiding obstacles encountered along the way. 


## Experiment
### SLMs with FastNav
![accuracy](/static/image/accuracy.png)
The accuracy of the SLMs and GPT4 on the test set during fine-tuning and iteration processes. It can be seen that all the SLMs accuracy rises gradually in both porcesses, and finally get close to that of GPT4. We recognize fine-tuning as the key to using SLMs, which obviously constraints their output format, and the teacher-student iteration is an effective way of futher improving their performance.

### Simulation Experiment
<div style="display: flex; justify-content: space-around; gap: 20px;">
    <div style="flex: 1; text-align: center; max-width: 45%;">
        <video width="100%" height="auto" controls autoplay muted>
            <source src="/static/videos/hospital_frontdesk4X.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
        <p>Please recharge the robot at the front desk</p>
    </div>
    <div style="flex: 1; text-align: center; max-width: 45%;">
        <video width="100%" height="auto" controls autoplay muted>
            <source src="/static/videos/hospital_delivery5X.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
        <p>Bring a bottle of water from the vending machine to bed 1.</p>
    </div>
</div>




### Real Experiment
<section class="hero is-light is-small">
  <div class="hero-body">
    <div class="container">
      <div id="results-carousel" class="carousel results-carousel">
        <div class="item has-text-centered">
          <video poster="" autoplay controls muted loop playsinline height="100%">
            <source src="/static/videos/1-0.mp4" type="video/mp4">
            Your browser does not support the video tag.
          </video>
          <p id="overlay"></p>
        </div>
        <div class="item has-text-centered">
          <video poster="" autoplay controls muted loop playsinline height="100%">
            <source src="/static/videos/1-0.mp4" type="video/mp4">
            Your browser does not support the video tag.
          </video>
          <p id="overlay"></p>
        </div>
        <div class="item has-text-centered">
          <video poster="" autoplay controls muted loop playsinline height="100%">
            <source src="/static/videos/1-0.mp4" type="video/mp4">
            Your browser does not support the video tag.
          </video>
          <p id="overlay"></p>
        </div>
        <div class="item has-text-centered">
          <video poster="" autoplay controls muted loop playsinline height="100%">
            <source src="/static/videos/1-0.mp4" type="video/mp4">
            Your browser does not support the video tag.
          </video>
          <p id="overlay"></p>
        </div>
        <div class="item has-text-centered">
          <video poster="" autoplay controls muted loop playsinline height="100%">
            <source src="/static/videos/1-0.mp4" type="video/mp4">
            Your browser does not support the video tag.
          </video>
          <p id="overlay"></p>
        </div>
        <div class="item has-text-centered">
          <video poster="" autoplay controls muted loop playsinline height="100%">
            <source src="/static/videos/1-0.mp4" type="video/mp4">
            Your browser does not support the video tag.
          </video>
          <p id="overlay"></p>
        </div>
      </div>
      <!-- Add Arrows -->
      <div class="carousel-arrow carousel-prev">&#10094;</div>
      <div class="carousel-arrow carousel-next">&#10095;</div>
    </div>
  </div>
</section>

<!-- CSS -->
<style>
  .hero.is-light {
    background-color: #f5f5f5;
  }

  .carousel {
    display: flex;
    overflow: hidden;
    position: relative;
  }

  .item {
    min-width: 100%;
    transition: transform 0.5s ease;
  }

  .carousel-arrow {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    font-size: 2em;
    color: #000;
    cursor: pointer;
    z-index: 10;
  }

  .carousel-prev {
    left: 10px;
  }

  .carousel-next {
    right: 10px;
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
  }

  video {
    width: 100%;
    height: auto;
  }

  #overlay {
    margin-top: 10px;
  }
</style>

<!-- JavaScript -->
<script>
  document.addEventListener('DOMContentLoaded', function() {
    let index = 0;
    const items = document.querySelectorAll('.carousel .item');
    const totalItems = items.length;

    document.querySelector('.carousel-next').addEventListener('click', function() {
      items[index].style.transform = `translateX(-100%)`;
      index = (index + 1) % totalItems;
      items[index].style.transform = `translateX(0)`;
    });

    document.querySelector('.carousel-prev').addEventListener('click', function() {
      items[index].style.transform = `translateX(-100%)`;
      index = (index - 1 + totalItems) % totalItems;
      items[index].style.transform = `translateX(0)`;
    });
  });
</script>


## Citation
```
@article{turing1936computable,
  title={On computable numbers, with an application to the Entscheidungsproblem},
  author={Turing, Alan Mathison},
  journal={Journal of Mathematics},
  volume={58},
  number={345-363},
  pages={5},
  year={1936}
}
```
