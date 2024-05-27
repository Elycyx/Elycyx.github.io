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
    <p><em>Figure 1: FastNav is a method for compressing large models for robot navigation.</em></p>
</div>


<!-- Using HTML to center the abstract -->
<div class="columns is-centered has-text-centered">
    <div class="column is-four-fifths">
        <h2>Abstract</h2>
        <div class="content has-text-justified">
As large language models (LLMs) develop rapidly, robots have started to enjoy the benefits that new control methods with large models bring. Because edge computing meets the requirements of fast response, privacy and network independence, we believe it is beneficial to the widespread of large models applied for robot navigation or even for various industries. In this paper, we propose a method for using lightweight LLMs, also known as small language models (SLMs), for robot navigation, which is called FastNav, a fine-tuned adaptive small-language-model trained for multi-point robot navigation. The proposed method contains three modules, fine-tuning, teacher-student iteration and robot navigation controller. We train and evaluate models with FastNav in both simulation environment and real robot, proving that we can deploy them with low cost but high accuracy and few response time. Compared to other compression methods, FastNav shows its huge potential in local deployment of large models and tends to be a promising solution for multi-point robot navigation.
        </div>
    </div>
</div>

---


## Approach
![Architecture](/static/image/Architecture.png)
### Fine-tuning

### Teacher-student Iteration

### Robot Navigation Controller



## Experiment

### Simulation Experiment
<div style="display: flex; justify-content: space-around;">
    <div style="flex: 1; text-align: center;">
        <video width="600" height="480" controls autoplay>
            <source src="/static/videos/hospital_frontdesk4X.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
        <p>Please recharge the robot at the front desk</p>
    </div>
    <div style="flex: 1; text-align: center;">
        <video width="600" height="480" controls autoplay>
            <source src="/static/videos/hospital_delivery5X.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
        <p>Bring a bottle of water from the vending machine to bed 1.</p>
    </div>
</div>


### Real Experiment

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
