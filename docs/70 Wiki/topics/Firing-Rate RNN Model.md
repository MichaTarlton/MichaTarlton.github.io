---
aliases: [FRRNN,]
type:  topics
status: open
project: Survey Paper
priority: p4
creationtag: 2022-06-08 17:31
infotags:[ SNN, RNN]
---
# From [[@zhouEncodingTimeNeural2022]]

## Firing-rate RNN model
RNNs were based on firing-rate units that obeyed Dale's law $(\mathrm{N}=200,80 / 20 \%$ excitatory/ inhibitory). RNN dynamics was described by the following equations:
$$
\begin{gathered}
\tau \frac{d \boldsymbol{x}}{d t}=-\boldsymbol{x}+\boldsymbol{W}^{\text {rec }} * \boldsymbol{r}+\boldsymbol{W}^{i \boldsymbol{n}} * \boldsymbol{I}+\sigma * \boldsymbol{N}(0,1) * \sqrt{2 * \tau} \\
o=\boldsymbol{W}^{\text {out }} * \boldsymbol{r} \\
\boldsymbol{r}=\min \left(\ln \left(1+e^{x}\right), 20\right)
\end{gathered}
$$
where $\mathbf{x} \in \mathbb{R}^{\mathrm{N} \times 1}$ represents the input currents of RNN units, and firing rate vector $\mathbf{r}$ is obtained by applying a Softplus function constrained by an upper bound of 20 . The time constant $\tau$ was equal to $100 \mathrm{~ms}$ for all units. $\mathbf{W}^{\text {in }} \in \mathbb{R}^{N \times 2}$ and $\mathbf{I}$ are the input weights and external inputs, which are task-specific as described below. Each unit received independent Gaussian noise $\mathbf{N}$ $(0,1)$ with the standard deviation of $\sigma \sqrt{2 \tau}$. Unless otherwise specified, $\sigma=0.45$. $\mathbf{W}^{\text {rec }} \in \mathbb{R}^{\mathrm{N} \times \mathrm{N}}$ is the recurrent weight matrix. Self-connections were absent in the network. The output $(o)$ of the network is computed linearly from the output weights $\mathbf{W}^{\text {out }}$ and $\mathbf{r}$. RNNs were implemented and trained in Tensorflow starting from the code of Kim et al [77,78].
Training. Networks were trained using adaptive moment estimation stochastic gradient descent algorithm (Adam) to minimize the error between network output $o$ and target $z$ :
$$
\text { Error }=\sqrt{\sum_{t=0}^{T}[o(t)-z(t)]^{2}}
$$
where $\mathrm{T}$ is the total length of a given trial. The target and mask are task-dependent as described below. The learning rate was $0.01$, and other TensorFlow default values were used.

Only recurrent weights $\mathbf{W}^{\text {rec }}$ and output weights $\mathbf{W}^{\text {out }}$ were trained. Unless otherwise specified, $\mathbf{W}^{\text {rec }}$ was initialized as a random sparse matrix with a connection probability of $0.2$ from a normal distribution with zero mean and standard deviation (gain) of 1 and transformed to absolute values. To begin in an approximately balanced regime the inhibitory weights were multiplied by 4 for the initialization but not for training. 

To respect Dale's law during training a rectified linear operation was applied on $\mathbf{W}^{\text {rec }}$ to clip the weights down to zero and then excitation and inhibition were implemented by multiplying the clipped $\mathbf{W}^{\text {rec }}$ with a diagonal matrix of 1 and $-1$ representing excitatory and inhibitory units, respectively $[78,79] . \mathbf{W}^{\text {in }}$ was drawn from a standard normal distribution and was fixed during training.

During training, a discretization step of $20 \mathrm{~ms}$ was used. After training, RNNs were ported to Matlab using the trained parameters and a discretization step of $1 \mathrm{~ms}$ was used to get the dynamics for analyses.

Parameters were updated every trial. After every 100 trials of training, the network was tested for 100 trials to compute the task performance (see below) and mean error. When task performance was higher than 97% and the mean error isl ower than 2, the training was considered a success and stopped.