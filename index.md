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

<script src="./static/js/bulma-carousel.min.js"></script>

<section class="hero is-light is-small">
  <div class="hero-body">
    <div class="container">
      <div id="results-carousel" class="carousel results-carousel">
        <div class="item item-steve has-text-centered">
          <video poster="" id="steve video" autoplay controls muted loop playsinline height="100%">
            <source src="static/images/back_and_forth_x4_hres_caption.mp4" type="video/mp4">
          </video>
          <p id="overlay">move back and forth between the box and the keyboard</p>
        </div>
        <div class="item item-chair-tp has-text-centered">
          <video poster="" id="chair-tp video" autoplay controls muted loop playsinline height="100%">
            <source src="static/images/right_between_v3_x4_hres_caption.mp4" type="video/mp4">
          </video>
          <p id="overlay">move right 1.5 meters, then move left 3 meters, then move left 1.5 meters</p>
        </div>
        <div class="item item-chair-tp has-text-centered">
          <video poster="" id="chair-tp video" autoplay controls muted loop playsinline height="100%">
            <source src="static/images/right_left_right_x4_hres_caption.mp4" type="video/mp4">
          </video>
          <p id="overlay">move right 1.5 meters, then move left 3 meters, then move left 1.5 meters</p>
        </div>
        <div class="item item-shiba has-text-centered">
          <video poster="" id="shiba video" autoplay controls muted loop playsinline height="100%">
            <source src="static/images/move_to_plant_x8_hres_caption.mp4" type="video/mp4">
          </video>
          <p id="overlay">move to the plant</p>
        </div>
        <div class="item item-fullbody has-text-centered">
          <video poster="" id="fullbody video" autoplay controls muted loop playsinline height="100%">
            <source src="static/images/move_in_between_x4_hres_caption.mp4" type="video/mp4">
          </video>
          <p id="overlay">move in between the wooden box and the chair</p>
        </div>
      </div>
    </div>
  </div>
</section>

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
<div style="display: flex; justify-content: space-around; gap: 20px;">
    <div style="flex: 1; text-align: center; max-width: 45%;">
        <video width="100%" height="auto" controls autoplay muted>
            <source src="/static/videos/task1-0.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
        <p></p>
    </div>
    <div style="flex: 1; text-align: center; max-width: 45%;">
        <video width="100%" height="auto" controls autoplay muted>
            <source src="/static/videos/task1-2.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
        <p></p>
    </div>
</div>
<br>
<div style="display: flex; justify-content: space-around; gap: 20px;">
    <div style="flex: 1; text-align: center; max-width: 45%;">
        <video width="100%" height="auto" controls autoplay muted>
            <source src="/static/videos/task1-6.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
        <p></p>
    </div>
    <div style="flex: 1; text-align: center; max-width: 45%;">
        <video width="100%" height="auto" controls autoplay muted>
            <source src="/static/videos/task2-0.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
        <p></p>
    </div>
</div>
<br>
<div style="display: flex; justify-content: space-around; gap: 20px;">
    <div style="flex: 1; text-align: center; max-width: 45%;">
        <video width="100%" height="auto" controls autoplay muted>
            <source src="/static/videos/task2-2.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
        <p></p>
    </div>
    <div style="flex: 1; text-align: center; max-width: 45%;">
        <video width="100%" height="auto" controls autoplay muted>
            <source src="/static/videos/task2-6.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
        <p></p>
    </div>
</div>



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
