---
created: 2022-05-09T17:15:24 (UTC +02:00)
tags: []
source: http://dprogrammer.org/rnn-lstm-gru
author: 
---

# RNN, LSTM & GRU



> ## Excerpt
> Recurrent Neural Network (RNN), Long-Short Term Memory (LSTM) & Gated Recurrent Unit (GRU) Tutorial and Examples

---
[Skip to content](http://dprogrammer.org/rnn-lstm-gru#content)

Recurrent Neural Network (RNN), Long-Short Term Memory (LSTM) & Gated Recurrent Unit (GRU)

![](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_1200/http://dprogrammer.org/wp-content/uploads/2019/04/RNN-vs-LSTM-vs-GRU-1200x361.png)

Is a type of artificial neural network where connections between nodes form a sequence. This allows temporal dynamic behavior for time sequence.  
There are 3 types of vanilla recurrent neural network: the simple (RNN), gated recurrent unit (GRU) and long short term memory unit (LSTM).

#### RNN – Recurrent Neural Network

---

##### Notation

![x_t](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_15,h_11/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-e61554f08003ee171b6d5c3f9eac71ae_l3.png "Rendered by QuickLaTeX.com") : input vector (![m \times 1](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_45,h_13/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-29e5110a60c64b5dad2e64b8fb7a7953_l3.png "Rendered by QuickLaTeX.com")).  
![h_t](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_15,h_16/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-ec35de23c67ce8f03c9ac543d88f9aba_l3.png "Rendered by QuickLaTeX.com") : hidden layer vector ![(n\times 1)](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_53,h_18/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-f4da819f11cd395ccec508b18538d33e_l3.png "Rendered by QuickLaTeX.com").  
![o_t](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_14,h_11/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-d4bfa32c729fb1c451b3564683c4ef97_l3.png "Rendered by QuickLaTeX.com") : output vector ![(n\times1)](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_53,h_18/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-cf242a77af9988999f8fac226f337803_l3.png "Rendered by QuickLaTeX.com").  
![b_h](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_16,h_16/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-9b474ba86eecd2e9932ffc09b0f82009_l3.png "Rendered by QuickLaTeX.com") : bias vector ![(n\times1)](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_53,h_18/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-cf242a77af9988999f8fac226f337803_l3.png "Rendered by QuickLaTeX.com").  
![U,W](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_38,h_16/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-a8d1f4b974f1f076828d6c220778b819_l3.png "Rendered by QuickLaTeX.com") : parameter matrices ![(n\times m)](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_60,h_18/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-a069d3f766abc4399b2c4f6e00d5dd14_l3.png "Rendered by QuickLaTeX.com").  
![V](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_14,h_12/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-f8a2d43be5bf9f50ad05bd6b23681c95_l3.png "Rendered by QuickLaTeX.com") : parameter matrix ![(n\times n)](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_55,h_18/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-94a39522758c3aca8ab213ee82b50a0b_l3.png "Rendered by QuickLaTeX.com").  
![\sigma_h, \sigma_y](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_44,h_14/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-80d61dd3965e209b3637566b725f099c_l3.png "Rendered by QuickLaTeX.com") : activation functions.

![](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_1374/http://dprogrammer.org/wp-content/uploads/2019/04/RNN_Core2.png)

##### Feed-Forward

    ![\[ h_t=\sigma_h(i_t)=\sigma_h(U_hx_t+V_hh_{t-1}+b_h) \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_289,h_18/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-5b03c40bc8c8e6b3585087d4093e3540_l3.png "Rendered by QuickLaTeX.com")

    ![\[ y_t=\sigma_y(a_t)=\sigma_y(W_yh_t+b_h) \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_219,h_19/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-d534204b8eb3728edc81a0ce7f46c1d7_l3.png "Rendered by QuickLaTeX.com")

##### Backpropagation

    ![\[ \Pi_t= \frac{\partial E_t}{\partial o_t} \frac{\partial o_t}{\partial h_t}+ \frac{\partial h_{t+1}}{\partial h_t} \Pi_{t+1} \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_210,h_39/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-816c6848972ac7eef60586e8eba6897b_l3.png "Rendered by QuickLaTeX.com")

    ![\[ \beta_t^U=\beta_{t+1}^U+\Pi_t \frac{\partial h_t}{\partial U_t} \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_151,h_39/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-ec6c06aff2749e2c3045f889d30b1be6_l3.png "Rendered by QuickLaTeX.com")

    ![\[ \beta_t^V=\beta_{t+1}^V+\Pi_t \frac{\partial h_t}{\partial V_t} \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_150,h_39/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-507f865b92bbf7f667b9d5cdf7120ddb_l3.png "Rendered by QuickLaTeX.com")

    ![\[ \beta_t^W=\beta_{t+1}^W+ \frac{\partial E_t}{\partial o_t} \frac{\partial o_t}{\partial W_t} \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_174,h_39/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-7e8536322967445192b2b8269598c29a_l3.png "Rendered by QuickLaTeX.com")

    ![\[ \frac{\partial E}{\partial X} \equiv \beta_0^x \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_71,h_38/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-a199d288a01ec9c70548bed2528f7175_l3.png "Rendered by QuickLaTeX.com")

##### Example

-   Vanilla mode of processing without RNN, from fixed-sized input to fixed-sized output (e.g. image classification).
-   Sequence output (e.g. image captioning takes an image and outputs a sentence of words).
-   Sequence input (e.g. sentiment analysis where a given sentence is classified as expressing positive or negative sentiment)
-   Sequence input and sequence output (e.g. Machine Translation: an RNN reads a sentence in English and then outputs a sentence in French).
-   Synced sequence input and output (e.g. video classification where we wish to label each frame of the video).

![](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_815/http://dprogrammer.org/wp-content/uploads/2019/04/Example-RNN.png)

#### LSTM – Long-Short Term Memory

---

##### Notation

![h_t](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_15,h_16/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-ec35de23c67ce8f03c9ac543d88f9aba_l3.png "Rendered by QuickLaTeX.com") , ![C_t](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_18,h_15/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-23fc106a6dc2a6f5fa1eaeb274911e5a_l3.png "Rendered by QuickLaTeX.com") : hidden layer vectors.  
![x_t](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_15,h_11/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-e61554f08003ee171b6d5c3f9eac71ae_l3.png "Rendered by QuickLaTeX.com") : input vector.  
![b_f](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_16,h_19/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-bdc988b6f815b9a00bed409aa5eac169_l3.png "Rendered by QuickLaTeX.com") , ![b_i](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_13,h_16/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-0c96df5706e08ddc96aa5ddb04fe9446_l3.png "Rendered by QuickLaTeX.com") , ![b_c](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_14,h_16/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-87872827d137ce528c4ab71009d6c5d5_l3.png "Rendered by QuickLaTeX.com") , ![b_o](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_15,h_16/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-077b3b0600ab38c5ac020c5e7f887f35_l3.png "Rendered by QuickLaTeX.com") : bias vector.  
![W_f](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_25,h_18/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-d692813c52d6d1fb0f2fb8c02d87c0ac_l3.png "Rendered by QuickLaTeX.com") , ![W_i](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_22,h_15/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-bbc0e4525b5337eae1896658ccaca8be_l3.png "Rendered by QuickLaTeX.com") , ![W_c](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_23,h_15/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-a5652251895933992507e39d9f4fb368_l3.png "Rendered by QuickLaTeX.com") , ![W_o](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_24,h_15/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-ef80e2b242538af71eecce45d523da93_l3.png "Rendered by QuickLaTeX.com") : parameter matrices.  
![\sigma](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_11,h_8/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-002db43cb4222d94b346ebaa548e03bd_l3.png "Rendered by QuickLaTeX.com") , ![\tanh](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_36,h_13/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-0b81e5017f469bbd09028667367a7e6a_l3.png "Rendered by QuickLaTeX.com") : activation functions.

![](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_1003/http://dprogrammer.org/wp-content/uploads/2019/04/LSTM-Core.png)

##### Feed-Forward

    ![\[ f_t=\sigma(W_f\cdot[h_{t-1},x_t]+b_f) \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_205,h_20/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-29f60b49619412f2281021705d731ae3_l3.png "Rendered by QuickLaTeX.com")

    ![\[ i_t=\sigma(W_i\cdot[h_{t-1},x_t]+b_i) \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_196,h_19/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-82f03ed88f42b4ab8513653a36b6e775_l3.png "Rendered by QuickLaTeX.com")

    ![\[ o_t=\sigma(W_o\cdot[h_{t-1},x_t]+b_o) \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_203,h_19/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-dbc53f6ce29f802f6d0a2d2bf75daf1c_l3.png "Rendered by QuickLaTeX.com")

    ![\[ \tilde{C}_t=\tanh(W_c\cdot[h_{t-1},x_t]+b_c) \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_230,h_22/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-4c8e4bdab43d69294e773a5814b5c9e2_l3.png "Rendered by QuickLaTeX.com")

    ![\[ C_t=f_t\odot C_{t-1}+i_t\odot\tilde{C}_t \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_187,h_21/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-831170c55091126028eede561ec2e3a0_l3.png "Rendered by QuickLaTeX.com")

    ![\[ h_t=o_t\odot\tanh(C_t) \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_143,h_18/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-3ea0dfc9c9edc4b4f4290ef313c99664_l3.png "Rendered by QuickLaTeX.com")

##### Backpropagation

    ![\begin{align*} &\frac{\partial C_{t+1}}{\partial h_t}= \frac{\partial C_{t+1}}{\partial \tilde{C}_{t+1}} \frac{\partial \tilde{C}_{t+1}}{\partial h_t}+ \frac{\partial C_{t+1}}{\partial f_{t+1}} \frac{\partial f_{t+1}}{\partial h_t}+ \frac{\partial C_{t+1}}{\partial t_{t+1}} \frac{\partial i_{t+1}}{\partial h_t}\\ &\frac{\partial C_{t+1}}{\partial C_t}\\ &\frac{\partial h_{t+1}}{\partial C_t}= \frac{\partial h_{t+1}}{\partial C_{t+1}} \frac{\partial C_{t+1}}{\partial C_t}\\ &\frac{\partial h_{t+1}}{\partial h_t}= \frac{\partial h_{t+1}}{\partial C_{t+1}} \frac{\partial C_{t+1}}{\partial h_t}+ \frac{\partial h_{t+1}}{\partial o_{t+1}} \frac{\partial o_{t+1}}{\partial h_t} \end{align*}](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_405,h_187/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-abf9a93846925b6a0594b32254fb6524_l3.png "Rendered by QuickLaTeX.com")

    ![\[ \Pi_t= \frac{\partial E_t}{\partial h_t}+ \frac{\partial h_{t+1}}{\partial h_t} \Pi_{t+1}+ \frac{\partial C_{t+1}}{\partial h_t} \mathcal{T}_{t+1} \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_286,h_39/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-65e5c6bfd19294738fb112d05884c84b_l3.png "Rendered by QuickLaTeX.com")

    ![\[ \mathcal{T}_t= \frac{\partial E_t}{\partial h_t} \frac{\partial E_t}{\partial C_t}+ \frac{\partial h_{t+1}}{\partial C_t} \Pi_{t+1}+ \frac{\partial C_{t+1}}{\partial C_t} \mathcal{T}_{t+1} \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_315,h_39/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-4439ae5346ea95daf7849f63a89c60ee_l3.png "Rendered by QuickLaTeX.com")

    ![\[ \beta_t^f=\beta_{t+1}^f+ \frac{\partial C_t}{\partial f_t} \frac{\partial f_t}{\partial W_t^f} ( \frac{\partial h_t}{\partial C_t} \Pi_t + \mathcal{T}_t ) \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_275,h_45/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-ff31700dfd6ffc36b8f2b3369b79a648_l3.png "Rendered by QuickLaTeX.com")

    ![\[ \beta_t^i=\beta_{t+1}^i+ \frac{\partial C_t}{\partial i_t} \frac{\partial i_t}{\partial W_t^i} ( \frac{\partial h_t}{\partial C_t} \Pi_t + \mathcal{T}_t ) \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_269,h_42/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-9b8bab5419d2c979dd95ad58f5113f10_l3.png "Rendered by QuickLaTeX.com")

    ![\[ \beta_t^c=\beta_{t+1}^c+ \frac{\partial C_t}{\partial \tilde{C}_{t}} \frac{\partial \tilde{C}_{t}}{\partial W_t^c} ( \frac{\partial h_t}{\partial C_t} \Pi_t + \mathcal{T}_t ) \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_271,h_46/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-d16a0880536e9072fbc3ffeef897e2e6_l3.png "Rendered by QuickLaTeX.com")

    ![\[ \beta_t^o=\beta_{t+1}^o+ \frac{\partial h_t}{\partial o_t} \frac{\partial o_t}{\partial W_t^o} ( \Pi_t ) \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_201,h_41/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-d710a5d575645b19e577e8240d5303dc_l3.png "Rendered by QuickLaTeX.com")

#### GRU – Gated Recurrent Unit

---

##### Notation

![h_t](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_15,h_16/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-ec35de23c67ce8f03c9ac543d88f9aba_l3.png "Rendered by QuickLaTeX.com") : hidden layer vectors.  
![x_t](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_15,h_11/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-e61554f08003ee171b6d5c3f9eac71ae_l3.png "Rendered by QuickLaTeX.com") : input vector.  
![b_z](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_15,h_16/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-bcc40872f04438803011ba752db2bc93_l3.png "Rendered by QuickLaTeX.com") , ![b_r](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_14,h_16/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-ac9b0a529e9f441b39c7bf0c4b20ccee_l3.png "Rendered by QuickLaTeX.com") , ![b_h](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_16,h_16/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-9b474ba86eecd2e9932ffc09b0f82009_l3.png "Rendered by QuickLaTeX.com") : bias vector.  
![W_z](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_24,h_15/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-a49f465f756f25df1fa651f8c3b746a2_l3.png "Rendered by QuickLaTeX.com") , ![W_r](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_23,h_15/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-8c936ce7ef7a7c4e20e72e4e46b2a868_l3.png "Rendered by QuickLaTeX.com") , ![W_h](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_25,h_15/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-79df7165f7d6cb2820d869f2b918c969_l3.png "Rendered by QuickLaTeX.com") : parameter matrices.  
![\sigma](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_11,h_8/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-002db43cb4222d94b346ebaa548e03bd_l3.png "Rendered by QuickLaTeX.com") , ![\tanh](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_36,h_13/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-0b81e5017f469bbd09028667367a7e6a_l3.png "Rendered by QuickLaTeX.com") : activation functions.

![](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_849/http://dprogrammer.org/wp-content/uploads/2019/04/GRU.png)

##### Feed-Forward

    ![\[ z_t=\sigma(W_z \cdot[h_{t-1},x_t]+b_z) \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_203,h_19/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-9afec6022fb4f854d5d9ffcfb6732b67_l3.png "Rendered by QuickLaTeX.com")

    ![\[ r_t=\sigma(W_r \cdot [h_{t-1},x_t]+b_r) \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_202,h_19/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-ad095108bdce174d9136f55447c6709a_l3.png "Rendered by QuickLaTeX.com")

    ![\[ \tilde{h}_t=\tanh(W_h\cdot[r_t \odot h_{t-1},x_t]+b_h) \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_267,h_22/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-697d42693149d97b00fed6d0030e4fb9_l3.png "Rendered by QuickLaTeX.com")

    ![\[ h_t=(1-z_t)\odot h_{t-1}+z_t\odot \tilde{h}_t \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_225,h_21/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-1382782b8d3f3a95e0eca0b8fd562314_l3.png "Rendered by QuickLaTeX.com")

##### Backpropagation

    ![\[ \frac{\partial h_{t+1}}{\partial h_t}= \frac{\partial h_{t+1}}{\partial h_t}+ \frac{\partial h_{t+1}}{\partial z_{t+1}} \frac{\partial z_{t+1}}{\partial h_t}+ \frac{\partial h_{t+1}}{\partial \tilde{h}_{t+1}} ( \frac{\partial \tilde{h}_{t+1}}{\partial h_t}+ \frac{\partial \tilde{h}_{t+1}}{\partial r_{t+1}} \frac{\partial r_{t+1}}{\partial h_t} ) \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_479,h_48/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-562505846cb1ba9e428c3a5ae4975d5f_l3.png "Rendered by QuickLaTeX.com")

    ![\[ \Pi_t= \frac{\partial E_t}{\partial h_t}+ \frac{\partial h_{t+1}}{\partial h_t} \Pi_{t+1} \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_180,h_39/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-0fc90a9571a9afc9a0eb6a603257739c_l3.png "Rendered by QuickLaTeX.com")

    ![\[ \beta_t^z=\beta_{t+1}^z+ \frac{\partial h_t}{\partial z_t} \frac{\partial z_t}{\partial W_t^z} \Pi_t \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_187,h_41/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-7b444f92540fd757bea1ed819c4715a7_l3.png "Rendered by QuickLaTeX.com")

    ![\[ \beta_t^r=\beta_{t+1}^r+ \frac{\partial h_t}{\partial \tilde{h}_t} \frac{\partial \tilde{h}_t}{\partial r_t} \frac{\partial r_t}{\partial W_t^r} \Pi_t \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_217,h_46/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-bba637750f22b2a5d7ed25036c831c6c_l3.png "Rendered by QuickLaTeX.com")

    ![\[ \beta_t^h=\beta_{t+1}^h+ \frac{\partial h_t}{\partial \tilde{h}_t} \frac{\partial \tilde{h}_t}{\partial W_t^h} \Pi_t \]](https://sp-ao.shortpixel.ai/client/q_glossy,ret_img,w_189,h_47/http://dprogrammer.org/wp-content/ql-cache/quicklatex.com-9bf825dbd01ffeaeb29952468d8fc449_l3.png "Rendered by QuickLaTeX.com")

-   [tweet 0](https://twitter.com/share?url=http%3A%2F%2Fdprogrammer.org%2Frnn-lstm-gru&text=RNN%2C%20LSTM%20%26%20GRU&via=DprogrammerL "Share on Twitter") 
-   [share 35](https://www.facebook.com/sharer/sharer.php?u=http%3A%2F%2Fdprogrammer.org%2Frnn-lstm-gru "Share on Facebook") 
-   [share](https://api.whatsapp.com/send?text=http%3A%2F%2Fdprogrammer.org%2Frnn-lstm-gru%20RNN%2C%20LSTM%20%26%20GRU "Share on Whatsapp") 
-   [share 0](https://www.reddit.com/submit?url=http%3A%2F%2Fdprogrammer.org%2Frnn-lstm-gru "Share on Reddit") 
-   [share](https://www.linkedin.com/shareArticle?mini=true&url=http%3A%2F%2Fdprogrammer.org%2Frnn-lstm-gru&title=RNN%2C%20LSTM%20%26%20GRU "Share on LinkedIn") 
-   [share 0](https://www.tumblr.com/widgets/share/tool?posttype=link&canonicalUrl=http%3A%2F%2Fdprogrammer.org%2Frnn-lstm-gru&tags=dprogrammer.org "Share on tumblr") 
-   [save 0](https://www.pinterest.com/pin/create/link/?url=http%3A%2F%2Fdprogrammer.org%2Frnn-lstm-gru&media=http%3A%2F%2Fdprogrammer.org%2Fwp-content%2Fuploads%2F2019%2F04%2FRNN-vs-LSTM-vs-GRU.png&description=RNN%2C%20LSTM%20%26%20GRU "Pin it on Pinterest")
