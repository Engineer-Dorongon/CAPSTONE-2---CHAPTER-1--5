### **3.3.3. Statistical Treatment of Classroom Navigation Usability (SOP 3)**

To evaluate the dynamic workability of SENSEY and test the navigation hypotheses, both descriptive and inferential statistical treatments are applied [15]. 

The analysis is structured into two sequential phases:

#### **A. Descriptive Statistics (Central Tendency and Variance)**
Before performing inferential hypothesis testing, the raw navigation completion times (mobility) and collision counts (safety) gathered across your $N = 30$ trials are summarized using descriptive indicators to establish your sample mean and standard deviation:

##### **1. The Sample Arithmetic Mean ($\bar{X}$):**
To calculate the average completion times, collision counts, and spatial awareness scores achieved by the subjects during the navigation trials, the standard arithmetic mean is used [15]:

$$\bar{X} = \frac{\sum_{i=1}^{N} X_i}{N}$$

Where:
*   $\bar{X}$ is the calculated sample mean [15].
*   $X_i$ represents the individual trial score (e.g., completion time in seconds) recorded during trial $i$ [15].
*   $N$ is the total number of navigation trials ($N = 30$).

##### **2. The Sample Standard Deviation ($s$):**
To measure the dispersion or variance of SENSEY's performance scores around the mean (proving system consistency across different runs), the sample standard deviation is used:

$$s = \sqrt{\frac{\sum_{i=1}^{N} (X_i - \bar{X})^2}{N - 1}}$$

Where:
*   $s$ is the calculated sample standard deviation.
*   $X_i$ represents the individual trial score [15].
*   $\bar{X}$ is the calculated sample mean.
*   $N$ is the total number of navigation trials ($N = 30$).

---

#### **B. Inferential Statistics (Hypothesis Testing)**
Once the descriptive sample mean ($\bar{X}$) and standard deviation ($s$) are established, they are used as inputs for **Inferential Statistics** to compare SENSEY's performance against traditional benchmarks [15]. 

Because the study compares the mean of a single experimental sample group ($N = 30$) against a known traditional mobility benchmark constant ($\mu_0 = 377\text{ seconds}$), a parametric **One-Sample $t$-test** is applied [15]:

$$t = \frac{\bar{X} - \mu_0}{\frac{s}{\sqrt{N}}}$$

Where:
*   $t$ is the calculated $t$-value compared against the critical $t$-value at a $95\%$ confidence level ($\alpha = 0.05$) [15].
*   $\bar{X}$ is SENSEY's descriptive sample mean calculated in Section A.
*   $\mu_0$ is the traditional mobility benchmark constant ($\mu_0 = 377\text{ seconds}$) [15].
*   $s$ is SENSEY's descriptive sample standard deviation calculated in Section A.
*   $N$ is the total number of navigation trials ($N = 30$) [15].
*   The degrees of freedom ($df$) for this test is defined as:
    $$df = N - 1 = 29$$

##### **The Decision Rule for Chapter 4:**
The calculated $t$-statistic is compared against the critical $t$-value at $df = 29$ and a significance level of **$\alpha = 0.05$**:
*   If the calculated $p$-value is **less than $0.05$** ($p < 0.05$), the **Null Hypothesis ($H_0$) is rejected and the Alternative Hypothesis ($H_a$) is accepted**, mathematically proving SENSEY provides a statistically significant improvement in the teacher's navigation speed and mobility compared to traditional benchmarks [15].
